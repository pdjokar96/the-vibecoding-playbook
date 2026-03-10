# Chapter 15: Deploying Your App — Going Live 🚀

You've built something amazing. It works on your computer. Your friends want to try it. Your future customers are waiting. But right now, your app lives on *your* machine — and nobody else can see it.

That's about to change.

**Deploying** means taking your app from your computer and putting it on the internet so anyone with a web browser can use it. Think of it like this: you've been cooking an incredible meal in your kitchen. Deploying is opening a restaurant so the world can taste it.

And here's the great news: deploying has never been easier or cheaper. Many platforms let you go live **for free**.

---

## What Actually Happens When You Deploy?

Right now, your app runs on `localhost` — that's your computer talking to itself. When you deploy, a company (like Vercel or Railway) takes your code, puts it on their powerful servers, and gives it a public web address (URL) that anyone can visit.

Here's the simplified flow:

```
Your Code (on GitHub)
        ↓
  Hosting Platform (Vercel, Railway, etc.)
        ↓
  Builds your app on their servers
        ↓
  Gives you a URL like: https://my-cool-app.vercel.app
        ↓
  Anyone in the world can visit it! 🌍
```

The best part? Most modern platforms connect directly to your GitHub repository. Every time you push new code, they automatically rebuild and redeploy your app. It's like magic.

---

## Choosing Where to Deploy

Not all apps are the same, and different types of apps need different hosting. Let's break it down simply.

### Static Sites (Frontend Only)

If your app is just HTML, CSS, and JavaScript — with no server or database — you have a **static site**. These are the simplest and cheapest to deploy.

**Best free options:**
| Platform | Free Tier | Best For |
|----------|-----------|----------|
| **Vercel** | 100 GB bandwidth/month | React, Next.js, any frontend |
| **Netlify** | 100 GB bandwidth/month | Any static site, forms |
| **Cloudflare Pages** | Unlimited bandwidth | Speed-focused sites |

### Full-Stack Apps (Frontend + Backend + Maybe a Database)

If your app has a server (handling logins, saving data, processing things), you need a platform that can run backend code too.

**Best free/cheap options:**
| Platform | Free Tier | Best For |
|----------|-----------|----------|
| **Railway** | $5 free credit/month | Full-stack apps, easy setup |
| **Render** | 750 hours/month free | Web services, background jobs |
| **Fly.io** | 3 shared VMs free | Apps needing global speed |

### Databases

If your app stores user data, you need a database that lives on the internet too (not just on your laptop).

**Best free options:**
| Platform | Free Tier | Best For |
|----------|-----------|----------|
| **Supabase** | 500 MB, 50K monthly active users | PostgreSQL + auth + storage |
| **Neon** | 512 MB storage | Serverless PostgreSQL |
| **PlanetScale** | 5 GB storage | MySQL, great scaling |

---

## Step-by-Step: Deploying a Static Site on Vercel

Vercel is one of the most popular and beginner-friendly platforms. Let's walk through deploying your first app.

### Prerequisites
- Your code is on GitHub (if you followed earlier chapters, it already is!)
- You have a Vercel account (free to create)

### Step 1: Sign Up for Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click **"Sign Up"**
3. Choose **"Continue with GitHub"** — this is the easiest option
4. Authorize Vercel to access your GitHub account

### Step 2: Import Your Project

1. Once logged in, click **"Add New Project"**
2. You'll see a list of your GitHub repositories
3. Find your project and click **"Import"**
4. Vercel will automatically detect what type of project it is (React, Next.js, plain HTML, etc.)

### Step 3: Configure Build Settings

Vercel is smart — it usually figures out the right settings automatically. But here's what to check:

- **Framework Preset**: Should match your project (e.g., "Next.js", "Create React App", "Other")
- **Build Command**: Usually `npm run build` — Vercel fills this in for you
- **Output Directory**: Usually `build` or `dist` or `.next` — again, auto-detected

If your project has **environment variables** (like API keys), click "Environment Variables" and add them now. We'll cover this in detail below.

### Step 4: Deploy!

1. Click **"Deploy"**
2. Watch the build logs — you'll see Vercel installing your dependencies and building your app
3. In about 30-60 seconds, you'll see a big green checkmark ✅
4. Your app is now live at a URL like `https://your-project-name.vercel.app`

### Step 5: Celebrate, Then Set Up Auto-Deploy

Here's the beautiful part: Vercel already set up auto-deploy. From now on, every time you push code to your `main` branch on GitHub, Vercel will automatically rebuild and update your live app. You don't have to do anything extra.

Even better: if you push to a different branch, Vercel creates a **preview deployment** — a temporary URL where you can test changes before they go live.

---

## Step-by-Step: Deploying a Full-Stack App on Railway

If your app has a backend (server, API, database), Railway is a fantastic choice. It feels like Vercel but for full-stack apps.

### Step 1: Sign Up for Railway

1. Go to [railway.app](https://railway.app)
2. Click **"Login"** → **"GitHub"**
3. Authorize Railway to access your GitHub

### Step 2: Create a New Project

1. Click **"New Project"**
2. Choose **"Deploy from GitHub repo"**
3. Select your repository

### Step 3: Add a Database (If Needed)

This is where Railway really shines:

1. In your project dashboard, click **"New"** → **"Database"**
2. Choose your database type (PostgreSQL is a great default)
3. Railway creates the database instantly and gives you connection details

### Step 4: Connect Your App to the Database

1. Click on your app service in the Railway dashboard
2. Go to the **"Variables"** tab
3. Railway can auto-inject database connection details. Click **"Add Reference"** and select your database's `DATABASE_URL`
4. Your app can now connect to the database using that environment variable

### Step 5: Configure and Deploy

1. Railway auto-detects your start command (like `npm start` or `python app.py`)
2. If it doesn't, go to **"Settings"** and set the **"Start Command"** manually
3. Click **"Deploy"** (or it might auto-deploy immediately)
4. Watch the build logs
5. Once deployed, go to **"Settings"** → **"Networking"** → **"Generate Domain"** to get a public URL

### Step 6: Verify Everything Works

Visit your Railway URL. Test:
- Can you see the homepage?
- Can you create an account / log in?
- Does data save and load correctly?
- Do all the features work like they did locally?

---

## Custom Domains: Using Your Own `.com`

Your app gets a free URL like `my-app.vercel.app`, which is fine for testing. But for a real business, you want something like `www.myawesomeapp.com`.

### Step 1: Buy a Domain

Popular domain registrars (places to buy domain names):

| Registrar | Typical Price | Notes |
|-----------|--------------|-------|
| **Namecheap** | $8-12/year | Great prices, easy interface |
| **Cloudflare Registrar** | At-cost pricing | Cheapest option, no markup |
| **Google Domains** | $12/year | Simple, integrates with Google |

> 💡 **Tip**: Don't overpay for a domain. A `.com` should cost $8-15/year. If someone is charging $30+, look elsewhere.

### Step 2: Connect Your Domain

The process is slightly different for each hosting platform, but the general steps are:

**On your hosting platform (e.g., Vercel):**
1. Go to your project settings
2. Find **"Domains"**
3. Add your custom domain (e.g., `myawesomeapp.com`)
4. The platform will give you DNS records to add

**On your domain registrar (e.g., Namecheap):**
1. Go to your domain's DNS settings
2. Add the records your hosting platform gave you (usually a `CNAME` or `A` record)
3. Wait 5-30 minutes for DNS to update (sometimes up to 48 hours, but usually fast)

**On Vercel specifically:**
1. Go to Project → Settings → Domains
2. Type your domain name and click "Add"
3. Vercel shows you exactly what DNS records to set
4. Add a `CNAME` record pointing to `cname.vercel-dns.com`
5. Vercel automatically sets up HTTPS (SSL) for free — your site gets the 🔒 padlock

---

## Environment Variables in Production

Remember those API keys and secrets you used during development? They need to live on your hosting platform too — but you should **never** put them directly in your code.

### What Are Environment Variables?

Think of them as secret notes your app can read but nobody can see in your code. Things like:
- API keys (for Stripe, OpenAI, etc.)
- Database connection strings
- Secret tokens for authentication

### Setting Environment Variables on Vercel

1. Go to your project on Vercel
2. Click **"Settings"** → **"Environment Variables"**
3. Add each variable:
   - **Name**: `STRIPE_SECRET_KEY`
   - **Value**: `your_stripe_key_here`
   - **Environment**: Choose which environments need it (Production, Preview, Development)
4. Click **"Save"**
5. **Redeploy** your app for the changes to take effect

### Setting Environment Variables on Railway

1. Go to your service in Railway
2. Click the **"Variables"** tab
3. Click **"New Variable"**
4. Add your key-value pair
5. Railway automatically redeploys when you add variables

> ⚠️ **Important**: Never commit a `.env` file to GitHub. Always add `.env` to your `.gitignore` file. Your secrets should only exist on your local machine and on your hosting platform.

---

## The Deploy Checklist ✅

Before you hit that deploy button, run through this checklist. Print it out, tape it to your monitor, make it your wallpaper — whatever works.

### Pre-Deploy Checklist

- [ ] **1. All features work locally** — test every feature on your computer first
- [ ] **2. Environment variables are set** — all API keys and secrets added to your hosting platform
- [ ] **3. `.env` is in `.gitignore`** — your secrets aren't being pushed to GitHub
- [ ] **4. Build succeeds locally** — run `npm run build` (or equivalent) and fix any errors
- [ ] **5. No console errors** — open your browser's developer tools and check for red errors
- [ ] **6. Images and assets load** — make sure file paths work (no broken images)
- [ ] **7. Mobile responsive** — resize your browser or check on your phone
- [ ] **8. Error pages exist** — what happens when someone visits a wrong URL? (404 page)
- [ ] **9. Database is set up in production** — your production database is created and connected
- [ ] **10. HTTPS is enabled** — your hosting platform should handle this, but double-check for the 🔒

> 💡 We also have a more detailed [Deploy Checklist Template](../../templates/deploy-checklist.md) in the templates folder!

---

## "My App Is Live!" — Testing Your Deployed App

Your app is deployed! Before you share it with the world, spend 10 minutes testing it properly.

### The Quick Smoke Test

1. **Visit your URL** in a regular browser window (not where you're logged into your hosting platform)
2. **Try the main user flow** — if it's a todo app, create a todo. If it's a booking tool, make a booking
3. **Test on your phone** — does it look good and work on a smaller screen?
4. **Open an incognito/private window** — test as a brand new user with no cached data
5. **Ask a friend to try it** — send someone the link and watch (or ask) how they experience it

### Things That Often Break After Deploying

- **API calls fail**: Your backend URL might still point to `localhost`. Update it to your production URL
- **Images don't load**: File paths that worked locally might not work in production. Check for case-sensitivity (local might ignore it, servers don't)
- **Login doesn't work**: OAuth callback URLs (Google login, etc.) need to be updated to your production domain
- **Database is empty**: Your production database is fresh — it won't have the test data from your laptop

---

## Common Deploy Problems and Fixes

### ❌ "Build Failed"

**What it means**: Your hosting platform tried to build your app and something went wrong.

**How to fix**:
1. Read the build logs — they tell you exactly what failed
2. Copy the error message and paste it to your AI assistant: *"My Vercel build failed with this error: [paste error]. How do I fix it?"*
3. Common culprits: missing dependencies, TypeScript errors, case-sensitive file names

### ❌ "Module Not Found"

**What it means**: Your app is trying to use a package that isn't installed.

**How to fix**:
1. Make sure all your dependencies are in `package.json` (not just installed globally on your machine)
2. Run `npm install` locally and commit the updated `package-lock.json`
3. Push to GitHub and redeploy

### ❌ "502 Bad Gateway" or "Application Error"

**What it means**: Your server started but crashed or isn't responding correctly.

**How to fix**:
1. Check the **runtime logs** (not build logs) on your hosting platform
2. Make sure your app listens on the correct port — many platforms set a `PORT` environment variable
3. Update your server code: `app.listen(process.env.PORT || 3000)`

### ❌ "CORS Error"

**What it means**: Your frontend is trying to talk to your backend but the browser is blocking it for security reasons.

**How to fix**:
1. Tell your AI: *"I'm getting a CORS error. My frontend is at [URL] and my backend is at [URL]. How do I fix CORS?"*
2. Usually involves adding your frontend URL to your backend's allowed origins

### ❌ "Environment Variable Is Undefined"

**What it means**: Your app is looking for a secret (like an API key) but can't find it.

**How to fix**:
1. Double-check the variable name — it must match exactly (they're case-sensitive)
2. Make sure you added it on your hosting platform, not just in your local `.env`
3. Redeploy after adding variables (some platforms require this)

### ❌ "Mixed Content" Warning

**What it means**: Your site uses HTTPS but is trying to load something over HTTP.

**How to fix**:
1. Find any `http://` URLs in your code and change them to `https://`
2. This includes API endpoints, image sources, and external scripts

---

## What's Next?

Your app is live on the internet! Real people can use it. That's an incredible accomplishment — seriously, most people never get this far. 🎉

But launching is just the beginning. In the next chapter, we'll talk about what happens *after* launch: tracking who's using your app, collecting feedback, and making it even better.

---

> **Key Takeaway**: Deploying doesn't have to be scary. Pick one platform (Vercel for static sites, Railway for full-stack), connect your GitHub, and push. Modern platforms make it almost impossible to mess up — and if you do, you can always redeploy.

[← Previous: Solopreneur Workflow](../14-solopreneur-workflow/README.md) | [Next: After Launch →](../16-after-launch/README.md)
