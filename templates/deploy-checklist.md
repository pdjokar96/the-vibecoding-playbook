# 🚀 Deployment Checklist

Go through this checklist every time you deploy your app. It catches the most common issues that trip people up.

**How to use**: Work through each item in order. Check it off when done. If something doesn't apply to your app, mark it N/A.

---

## Before You Deploy

- [ ] **1. App builds successfully on your machine**
  - Run your build command locally (e.g., `npm run build`)
  - Fix any errors or warnings before deploying
  - If the build fails locally, it will fail on the hosting platform too

- [ ] **2. All features work locally**
  - Open your app in the browser and test every main feature
  - Test the complete user flow: sign up → use the app → log out → log back in
  - Check on both desktop and mobile (resize your browser window)

- [ ] **3. No console errors in the browser**
  - Open Developer Tools (F12 or right-click → Inspect → Console)
  - Navigate through your app and check for red error messages
  - Fix any errors — even ones that seem harmless. They often cause real problems in production

- [ ] **4. Environment variables are configured**
  - List all the environment variables your app needs (check your `.env` file)
  - Add each one to your hosting platform's environment variable settings
  - Double-check: variable names must match exactly (they're case-sensitive!)
  - Remember: you may need different values for production vs. development (e.g., Stripe live keys vs. test keys)

- [ ] **5. `.env` is in `.gitignore`**
  - Verify that `.env`, `.env.local`, and `.env.production.local` are listed in `.gitignore`
  - Check your GitHub repo — make sure no `.env` files are visible there
  - If you accidentally committed secrets, rotate them (generate new keys) immediately

- [ ] **6. Database is set up for production**
  - Your production database is created (Supabase, Neon, PlanetScale, etc.)
  - Database tables/schema are created (run migrations if needed)
  - The production database connection string is set as an environment variable
  - Row Level Security (RLS) is enabled if using Supabase
  - Test: can your app connect to the production database?

---

## During Deployment

- [ ] **7. Build completes without errors**
  - Watch the build logs on your hosting platform
  - If the build fails, read the error message carefully
  - Common issues: missing dependencies, TypeScript errors, case-sensitive file names
  - Copy any errors and ask your AI: *"My deploy build failed with this error: [paste]. How do I fix it?"*

- [ ] **8. Deployment URL is accessible**
  - Visit the URL your hosting platform gives you (e.g., `your-app.vercel.app`)
  - If you see a generic error page, check the runtime logs (not build logs)
  - Make sure your app loads fully — not just the HTML, but styles, images, and data too

---

## After Deployment

- [ ] **9. Test the production app as a new user**
  - Open an incognito/private browser window
  - Visit your production URL
  - Sign up with a brand new account
  - Complete the main user flow from start to finish
  - Check: does everything work the same as it did locally?

- [ ] **10. Verify external services are connected**
  - Test any third-party integrations: payment processing, email sending, file uploads, AI features
  - These often fail first because of different API keys, webhook URLs, or CORS settings
  - Update OAuth callback URLs if using social logins (Google, GitHub, etc.) to use your production domain

- [ ] **11. HTTPS is working (🔒 padlock visible)**
  - Check that your URL shows `https://` and the padlock icon
  - Most platforms handle this automatically, but verify it's active
  - If using a custom domain, SSL may take a few minutes to activate

- [ ] **12. Custom domain is connected (if applicable)**
  - If using a custom domain, verify it resolves to your app
  - Test both `yourdomain.com` and `www.yourdomain.com`
  - Check that DNS records are correctly set up
  - SSL certificate is active for your custom domain

---

## Post-Deploy Quick Tests

Run through these in 5 minutes to catch the most common post-deploy issues:

| Test | How to Check | Common Fix |
|------|-------------|------------|
| Homepage loads | Visit your URL | Check build logs |
| Styles look correct | Visual inspection | Clear CDN cache, check CSS build |
| Images load | Visual inspection | Check file paths (case-sensitive on servers!) |
| Login works | Try logging in | Check auth environment variables |
| Data loads | Navigate to pages with data | Check database connection string |
| Forms submit | Fill out and submit a form | Check API endpoint URLs |
| Payments work | Do a test transaction (use test keys!) | Check Stripe/payment env variables |
| Emails send | Trigger an email action | Check email service configuration |

---

## If Something Goes Wrong

1. **Don't panic** — you can always roll back to a previous deployment
2. **Read the logs** — your hosting platform has both build logs and runtime logs
3. **Ask your AI** — paste the error message and ask for help
4. **Roll back** — most platforms let you redeploy a previous working version instantly:
   - **Vercel**: Go to Deployments → click on a previous successful deployment → Promote to Production
   - **Railway**: Use the deployment history to roll back
   - **Netlify**: Go to Deploys → click on a previous deploy → Publish Deploy

---

## Auto-Deploy Setup

Once your first deploy is working, set up auto-deploy so future changes go live automatically:

- [ ] GitHub repo is connected to your hosting platform
- [ ] Pushes to `main` branch trigger automatic deployments
- [ ] Preview deployments are enabled for other branches (so you can test before going live)

---

> 💡 **Pro tip**: Keep this checklist handy. The first deploy is the hardest. After that, auto-deploy handles everything — you just push code and it goes live. But it's still worth running through items 9-12 after any major changes.
