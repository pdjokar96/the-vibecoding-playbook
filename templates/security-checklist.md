# 🔒 Pre-Launch Security Checklist

Review this checklist before deploying your app to production. You don't need to be a security expert — just go through each item and address what applies to your app.

**How to use**: Go through each item. Check it off when done. If an item doesn't apply to your app, mark it N/A and move on.

---

## Authentication & Authorization

- [ ] **1. Passwords are hashed, not stored in plain text**
  - If you're using Supabase Auth, Firebase Auth, or Clerk — this is handled for you automatically ✅
  - If you built custom auth, ask your AI: *"Is my password storage secure? Show me how the passwords are being stored."*

- [ ] **2. Protected routes actually require login**
  - Visit your app's protected pages (dashboard, settings, etc.) in an incognito/private browser window *without* logging in
  - If you can see protected content without logging in, that's a bug — fix it!
  - Test API endpoints too: can you hit `/api/user/data` without being authenticated?

- [ ] **3. Users can only access their own data**
  - Log in as User A. Note the URL for their data (e.g., `/projects/123`)
  - Log in as User B in a different browser. Try visiting User A's URL
  - If User B can see User A's data, you need to add authorization checks
  - If using Supabase, enable Row Level Security (RLS) on all tables

---

## Secrets & Environment Variables

- [ ] **4. No API keys or secrets in your code**
  - Search your codebase for any hardcoded keys: `grep -r "sk_" .` or `grep -r "api_key" .`
  - All secrets should be in `.env` files locally and environment variables in production
  - Check: Can you see any secrets if you view your page source in the browser? (Right-click → View Source)

- [ ] **5. `.env` file is in `.gitignore`**
  - Open your `.gitignore` file and make sure `.env`, `.env.local`, and `.env.production` are listed
  - Check your GitHub repo — if `.env` was ever committed, the secrets are exposed even if you delete the file later
  - If secrets were exposed: rotate them (generate new keys) immediately

- [ ] **6. Client-side code only has public keys**
  - Environment variables starting with `NEXT_PUBLIC_` (Next.js) or `VITE_` (Vite) are visible to everyone
  - Only put truly public values there (like a Supabase URL or a Stripe publishable key)
  - Secret keys (Stripe secret key, database passwords) should NEVER have these prefixes

---

## Input Validation & Data Safety

- [ ] **7. All user inputs are validated**
  - Try submitting forms with: empty fields, extremely long text (10,000 characters), special characters (`<script>alert('hi')</script>`), negative numbers, emoji
  - Your app should handle all of these gracefully — show an error message, not crash

- [ ] **8. No SQL injection or XSS vulnerabilities**
  - If using an ORM (Prisma) or Supabase client library, you're mostly protected
  - Never build database queries by concatenating user input into strings
  - Ask your AI: *"Review my database queries for SQL injection vulnerabilities"*
  - For XSS: make sure user-generated content is escaped when displayed (React does this by default — but watch out for `dangerouslySetInnerHTML`)

- [ ] **9. File uploads are restricted (if applicable)**
  - If your app allows file uploads, restrict: file types (only allow images, PDFs, etc.), file size (set a maximum, e.g., 10MB), and file names (sanitize them)
  - Never let users upload executable files (.exe, .sh, .bat)
  - Store uploaded files in a dedicated storage service (Supabase Storage, Cloudflare R2), not in your app directory

---

## HTTPS & Network Security

- [ ] **10. HTTPS is enabled (your site has the 🔒 padlock)**
  - Most hosting platforms (Vercel, Netlify, Railway) provide this automatically
  - Visit your production URL — look for `https://` and the padlock icon
  - If your site loads over `http://`, check your hosting platform's SSL settings

- [ ] **11. API endpoints use HTTPS**
  - If your frontend calls external APIs, make sure all URLs start with `https://`
  - Search your code for `http://` — change any API calls to `https://`
  - This prevents data from being intercepted in transit

---

## Data Protection

- [ ] **12. Database backups are enabled**
  - If using Supabase (Pro plan), backups are automatic
  - If using Railway or other services, check if backups are available
  - At minimum, know how to export your data if needed

- [ ] **13. Sensitive data is handled carefully**
  - Don't log sensitive information (passwords, API keys, credit card numbers) in your console or error logs
  - If you store personal data (names, emails, addresses), have a privacy policy
  - Consider: what data do you *actually* need? Don't collect more than necessary

---

## Production Readiness

- [ ] **14. Error messages don't expose internals**
  - When something goes wrong, users should see a friendly message like "Something went wrong. Please try again."
  - They should NOT see database errors, stack traces, or internal paths
  - Check: break something intentionally in production and see what error message appears

- [ ] **15. Rate limiting is in place for sensitive endpoints**
  - Login attempts should be limited (e.g., 5 attempts per minute) to prevent brute force attacks
  - API endpoints that cost you money (AI calls, email sends) should have rate limits
  - If using Vercel or Cloudflare, they offer built-in rate limiting options
  - Ask your AI: *"Add rate limiting to my login endpoint and my API routes"*

---

## Quick Security Prompt for Your AI

If you want a thorough review, paste this to your AI assistant:

```
Please review my app for security issues. Here are my key files:

[Paste your auth code]
[Paste your API routes]
[Paste your database queries]

Check for:
1. Exposed secrets or API keys
2. Missing authentication on protected routes
3. Users accessing other users' data
4. Input validation gaps
5. XSS or injection vulnerabilities

For each issue, explain the risk simply and show me how to fix it.
```

---

## After You Launch

Security isn't a one-time thing. Keep these habits:

- **Update dependencies monthly**: Run `npm audit` and `npm update` regularly
- **Rotate API keys** if you ever suspect they've been exposed
- **Monitor for unusual activity**: Sudden spikes in traffic or database usage could indicate an attack
- **Keep learning**: Follow security best practices as your app grows

---

> 💡 **Remember**: Perfect security doesn't exist. The goal is to be reasonably secure — to close the obvious doors and not leave your keys under the mat. Following this checklist puts you ahead of most small apps on the internet.
