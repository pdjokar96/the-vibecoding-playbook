# 🚀 Prompts for Deployment

> You built the thing — now let's put it on the internet! Deployment can feel scary, but it's mostly just following steps. These prompts will help you launch your app, connect a domain, and keep everything running smoothly. Swap out the `[placeholders]` with your own details!

---

## Deploying to Vercel

### 1. First deploy to Vercel

```
I've never deployed an app before. I have a [Next.js / React / static HTML]
app in a GitHub repository called [repo name]. Walk me through deploying it
to Vercel step by step.

Include:
- How to create a Vercel account (free tier)
- How to connect my GitHub repo
- What settings to configure (build command, output directory, etc.)
- How to trigger the first deploy
- How to check if it worked
- What the free tier limits are

Assume I know nothing. Screenshots aren't possible, so describe exactly what
to click and where.
```

### 2. Fix a Vercel deploy that failed

```
My Vercel deployment just failed. Here's the build log:

[paste the build log or error messages from Vercel's dashboard]

My app uses [list your tech stack: Next.js, React, Tailwind, Supabase, etc.].

Can you:
1. Explain what went wrong in plain English
2. Show me exactly how to fix it
3. Tell me how to redeploy after fixing
```

---

## Deploying to Netlify

### 3. Deploy to Netlify

```
I have a [React / static HTML / Astro / etc.] project in a GitHub repository.
I want to deploy it to Netlify for free. Walk me through:

1. Creating a Netlify account
2. Connecting my GitHub repo
3. Configuring the build settings (build command, publish directory)
4. What a netlify.toml file is and if I need one
5. How to trigger a deploy
6. How to check my live site URL

I'm a complete beginner — please explain every step.
```

---

## Deploying to Railway

### 4. Deploy a full-stack app to Railway

```
I have a full-stack app with:
- Frontend: [React / Next.js / etc.]
- Backend: [Node.js / Express / etc.]
- Database: [PostgreSQL / MySQL / etc.]

I want to deploy everything to Railway. Walk me through:

1. Creating a Railway account
2. Setting up the project and services
3. Adding a database
4. Connecting my frontend and backend
5. Setting up environment variables
6. Deploying and verifying everything works

What will this cost on Railway's free/starter plan? Are there any limits
I should know about?
```

---

## Setting Up Custom Domains

### 5. Connect a custom domain

```
I just bought a domain name ([your-domain.com]) from [Namecheap / GoDaddy /
Google Domains / Cloudflare / etc.]. My app is deployed on [Vercel / Netlify /
Railway].

Walk me through connecting my custom domain:

1. What DNS records do I need to add? (be specific — which type, name, and value)
2. Where exactly do I add them in my domain registrar's dashboard?
3. How do I configure the domain in [my hosting platform]'s settings?
4. How long does it take for the domain to start working?
5. How do I get a free SSL certificate (https)?
6. How do I set up www.my-domain.com to redirect to my-domain.com (or vice versa)?
```

### 6. Troubleshoot domain issues

```
I connected my custom domain [your-domain.com] to [Vercel / Netlify /
Railway] but it's not working. Here's what I see:

- When I visit my domain: [describe what happens — error page? wrong site?
  "DNS not found"? takes forever to load?]
- I set up these DNS records: [list what you configured]
- It's been [time] since I made the changes

What could be wrong? Walk me through diagnosing and fixing this.
```

---

## Configuring Environment Variables

### 7. Set up environment variables

```
My app uses API keys and secrets that I don't want in my code. I need to
set up environment variables. I'm deploying on [Vercel / Netlify / Railway].

My app needs these variables:
- [VARIABLE_NAME_1] (for [what it's used for])
- [VARIABLE_NAME_2] (for [what it's used for])

Can you explain:
1. What environment variables are (in simple terms)
2. How to add them in [my hosting platform]'s dashboard
3. How to use them in my [Next.js / React / Node.js] code
4. How to set up a .env.local file for local development
5. How to make sure my .env files never get uploaded to GitHub
6. The difference between public and private environment variables
```

### 8. My environment variables aren't working

```
I set up environment variables on [Vercel / Netlify / Railway] but my app
can't find them. It keeps saying [paste the error, e.g., "API key is
undefined" or "process.env.MY_VAR is undefined"].

Here's how I'm trying to use the variable in my code:
[paste the relevant code]

Here's what I named the variable in my hosting dashboard: [variable name]

What am I doing wrong? Common issues are fine to list — I'll check each one.
```

---

## Troubleshooting Deploy Failures

### 9. General deploy failure troubleshooting

```
My deployment to [platform] keeps failing. Here's the full error log:

[paste the entire build/deploy log]

My project uses:
- Framework: [Next.js / React / etc.]
- Package manager: [npm / yarn / pnpm]
- Node version: [if you know it]

Can you:
1. Tell me what the error means in plain English
2. Identify the root cause
3. Give me the exact steps/commands to fix it
4. Tell me how to verify the fix locally before redeploying
```

### 10. "It works locally but not in production"

```
My app works perfectly on my computer (localhost) but breaks when I deploy
it to [Vercel / Netlify / Railway].

Here's what's different in production:
- [Describe the problem: features that don't work, pages that crash, etc.]

Here's the error from the production console/logs:
[paste any errors you can find]

What are the most common reasons an app works locally but breaks in
production? Walk me through checking each one. I'm using [your tech stack].
```

---

## Setting Up CI/CD

### 11. Set up automatic deploys

```
I want my app to automatically deploy whenever I push code to GitHub.
I'm using [Vercel / Netlify / Railway] and my code is on GitHub.

Walk me through:
1. Connecting my GitHub repo to my hosting platform (if not already done)
2. Setting up automatic deploys from the "main" branch
3. Setting up preview deploys for pull requests (so I can test changes
   before they go live)
4. How to manually trigger a deploy if I need to

Explain what's happening behind the scenes so I understand the flow:
code change → GitHub → hosting platform → live site.
```

### 12. Set up a simple GitHub Actions workflow

```
I want to add a basic GitHub Actions workflow to my project that:
- Runs whenever I push code to the "main" branch
- Installs dependencies
- Runs my build command to check for errors
- [Optional: runs tests if I have them]

I'm using [Node.js / npm] and my build command is [npm run build].

Create the workflow YAML file for me. Tell me:
1. Where to put the file in my project
2. What each part of the YAML does (comment every section)
3. How to check if the workflow ran successfully on GitHub
4. What to do if it fails
```

### 13. Add a pre-deploy checklist

```
I keep deploying my app and then finding problems. Create a pre-deploy
checklist I can go through every time before I push to production.

My app is a [describe your app] built with [your tech stack] and deployed
on [your platform].

Include checks for:
- Code quality
- Environment variables
- Build and tests
- Security basics
- Performance basics
- SEO basics (if it's a website)
- Backup and rollback plan

Make it a simple checkbox-style list I can copy and reuse.
```

---

## 💡 Tips for Smooth Deployments

- **Deploy early, deploy often.** Don't wait until your app is "done." Deploy on day one, even if it just shows "Hello World." The earlier you deploy, the easier it is to fix issues.
- **Read the error logs.** They look intimidating, but they almost always tell you exactly what's wrong. Paste them into AI and ask for a translation.
- **Check your environment variables.** 90% of "it works locally but not in production" problems are missing or misconfigured environment variables.
- **Keep your `main` branch deployable.** Only merge code that works. Use branches for experiments.
- **Know how to roll back.** On most platforms, you can instantly redeploy a previous working version. Learn how to do this BEFORE you need it.
- **Free tiers are generous.** Vercel, Netlify, and Railway all have free plans that are more than enough for launching your first apps.

---

*Part of [The Vibe Coding Playbook](../README.md) — a guide for building real apps with zero coding experience.*
