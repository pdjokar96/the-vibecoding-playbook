# Chapter 12: MCP Servers — Plug-and-Play Superpowers

> **What you'll learn:** How to give your AI the ability to *do* things — not just write code, but actually talk to Figma, Stripe, your database, and more. Think of it as installing superpowers. 🦸

---

## What Is MCP? (Explained for Non-Coders)

Let's start with a simple picture.

Right now, your AI coding assistant (Cursor, Claude, etc.) is incredibly smart — but it lives in a box. It can read your code, write new code, and answer questions. But it can't *reach out* and touch anything in the real world. It can't check your database. It can't look at your Figma design. It can't create a Stripe product for you.

**MCP (Model Context Protocol) gives your AI a phone.**

Specifically, it lets your AI call other apps and services directly — Figma, Stripe, Supabase, GitHub, and dozens more. It's the difference between:

- ❌ *"Here's some code that should connect to Stripe — go figure out how to run it."*
- ✅ *"I just created a product called 'Pro Plan' in your Stripe account with a $29/month price. Here's the checkout link."*

### The Plugin Analogy

Think of MCP servers like **browser extensions** or **phone apps**:

- Your phone (the AI) is useful on its own
- But installing Instagram gives it the power to share photos
- Installing Uber gives it the power to call a ride
- Installing your banking app gives it the power to manage money

MCP servers work the same way. Each one is a small "plugin" that teaches your AI how to talk to a specific service. Install the Stripe MCP? Now your AI speaks Stripe. Install the Figma MCP? Now your AI can see and understand your designs.

### Hands, Not Just a Mouth

Here's the key shift: without MCP, your AI has a **mouth** — it can *talk about* how to integrate Stripe or query a database. With MCP, your AI gets **hands** — it can actually *do* those things for you.

That's a game-changer for solopreneurs. You're not just getting code suggestions anymore. You're getting a teammate who can reach into your tools and get stuff done.

---

## Why MCP Matters for Solopreneurs

If you're building an app solo, you wear every hat — designer, developer, database admin, payment processor, DevOps engineer. MCP lets you take some of those hats off.

### Before MCP

1. Design your UI in Figma
2. Manually recreate it in code (or learn how to export it)
3. Read the Stripe API docs (50+ pages)
4. Write integration code for payments
5. Set up a database, learn SQL, write queries
6. Debug everything when it breaks

### After MCP

1. Design your UI in Figma
2. Tell your AI: *"Turn my Figma design into a Next.js page"* → Done ✅
3. Tell your AI: *"Set up a $29/month subscription product in Stripe"* → Done ✅
4. Tell your AI: *"Create a users table with email and plan columns"* → Done ✅

**The time savings are real.** Tasks that used to take hours of reading documentation and writing boilerplate code now take minutes of conversation.

> 💡 **The big idea:** MCP doesn't replace your AI — it *unlocks* it. Your AI already knows how Stripe works. MCP just gives it permission and a connection to actually use that knowledge on *your* account.

### Fewer Errors, Less Frustration

When your AI has direct access to a service through MCP, it can:

- **Verify things are working** instead of guessing
- **Use the correct, up-to-date API** instead of hallucinating outdated methods
- **Handle the boring parts** (authentication, formatting, error handling) automatically

You focus on *what* you want to build. MCP handles *how* to connect the pieces.

---

## The Solopreneur's MCP Toolkit

Here are the MCP servers that matter most when you're building a real product. You don't need all of them — pick the ones that match what you're building.

### 🎨 Design → Code

| MCP Server | What It Does |
|---|---|
| **Figma MCP** | Connects your AI to your Figma files. It can read your designs — layouts, colors, fonts, spacing — and understand what you're trying to build. |
| **Figma Make** | Goes a step further: it can turn Figma designs directly into working frontend code (React, HTML/CSS, etc.). |

**When to use it:** You've designed a landing page, dashboard, or app screen in Figma and you want your AI to build it *exactly* as designed — not some approximation.

**Example prompt:**
```
Look at my Figma file for the pricing page. Convert it to a React component
using Tailwind CSS. Match the colors, spacing, and fonts exactly.
```

### 🗄️ Databases

| MCP Server | What It Does |
|---|---|
| **Supabase MCP** | Connects to your Supabase project. Your AI can create tables, insert data, write queries, set up Row Level Security, and manage your entire backend. |
| **Neon MCP** | Similar to Supabase but for Neon's serverless Postgres. Great for managing database branches and running queries. |

**When to use it:** Anytime you need to store or retrieve data — user accounts, blog posts, products, orders, etc.

**Example prompt:**
```
Create a "products" table in my Supabase database with columns for
name, description, price, image_url, and created_at. Then insert
three sample products.
```

### 💳 Payments

| MCP Server | What It Does |
|---|---|
| **Stripe MCP** | Connects to your Stripe account. Your AI can create products, set prices, generate checkout links, manage subscriptions, and even look up payment history. |

**When to use it:** You're ready to charge money — subscriptions, one-time purchases, or any payment flow.

**Example prompt:**
```
Create a product called "Pro Plan" in Stripe with a monthly price of $29
and a yearly price of $249. Then generate a checkout link for the monthly plan.
```

### 📧 Email & Communications

| MCP Server | What It Does |
|---|---|
| **Resend MCP** | Send transactional emails — welcome emails, password resets, receipts, notifications. |
| **Twilio MCP** | Send SMS messages, make phone calls, set up two-factor authentication. |

**When to use it:** You need to communicate with your users beyond just the app itself.

**Example prompt:**
```
Using Resend, send a welcome email to new users when they sign up.
The email should include their name and a getting-started guide link.
```

### 📊 Analytics

| MCP Server | What It Does |
|---|---|
| **PostHog MCP** | Track user behavior, set up funnels, create dashboards, analyze feature usage. |

**When to use it:** You've launched and you want to understand what users are actually doing in your app.

**Example prompt:**
```
Set up PostHog tracking for my sign-up flow. I want to see how many
users start the form vs. complete it, and where they drop off.
```

### 🔍 Search & Data

| MCP Server | What It Does |
|---|---|
| **Brave Search MCP** | Lets your AI search the web for current information — docs, tutorials, real-time data. |
| **Web scraping MCPs** | Pull structured data from websites — competitor pricing, product listings, public datasets. |

**When to use it:** Your AI needs up-to-date information from the internet, or you need to gather data from other sites.

### 🐙 Version Control

| MCP Server | What It Does |
|---|---|
| **GitHub MCP** | Manage your repositories, create issues, open pull requests, review code, manage releases — all through your AI. |

**When to use it:** You're using GitHub to store your code (which you should be!) and want your AI to help manage the project.

**Example prompt:**
```
Create a GitHub issue titled "Add dark mode support" with a description
of what needs to change. Label it as "enhancement".
```

---

## How to Install & Configure an MCP Server

This is the hands-on section. We'll walk through the exact steps to get an MCP server running in your AI tool. The process is similar for most MCP servers — once you've done it once, you can do it for any of them.

### Step 1: Find the MCP Server

Most MCP servers live on GitHub. Here's how to find them:

1. Go to [github.com](https://github.com)
2. Search for the MCP server you want (e.g., `stripe mcp server` or `supabase mcp server`)
3. Look for the official repository — it'll usually have clear setup instructions in its README
4. You can also browse the [MCP server directory](https://github.com/modelcontextprotocol/servers) for a curated list

> 💡 **Tip:** The official MCP servers repository at `modelcontextprotocol/servers` is a great starting point. It lists dozens of verified, community-maintained servers.

### Step 2: Add It to Your MCP Config File

This is where the magic happens. Your AI tool has a config file that tells it which MCP servers to use. You just need to add a few lines of JSON.

#### For Cursor

The config file lives at the root of your project:

```
your-project/
├── .cursor/
│   └── mcp.json       ← This file
├── src/
├── package.json
└── ...
```

Open (or create) `.cursor/mcp.json` and add your MCP server:

```json
{
  "mcpServers": {
    "stripe": {
      "command": "npx",
      "args": ["-y", "@stripe/mcp", "--tools=all"],
      "env": {
        "STRIPE_SECRET_KEY": "sk_test_your_key_here"
      }
    }
  }
}
```

You can add multiple servers in the same file:

```json
{
  "mcpServers": {
    "stripe": {
      "command": "npx",
      "args": ["-y", "@stripe/mcp", "--tools=all"],
      "env": {
        "STRIPE_SECRET_KEY": "sk_test_your_key_here"
      }
    },
    "supabase": {
      "command": "npx",
      "args": ["-y", "@supabase/mcp"],
      "env": {
        "SUPABASE_URL": "https://your-project.supabase.co",
        "SUPABASE_SERVICE_ROLE_KEY": "your_service_role_key"
      }
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token_here"
      }
    }
  }
}
```

#### For Claude Desktop

The config file is in your system's app config directory:

- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`

The format is the same:

```json
{
  "mcpServers": {
    "stripe": {
      "command": "npx",
      "args": ["-y", "@stripe/mcp", "--tools=all"],
      "env": {
        "STRIPE_SECRET_KEY": "sk_test_your_key_here"
      }
    },
    "supabase": {
      "command": "npx",
      "args": ["-y", "@supabase/mcp"],
      "env": {
        "SUPABASE_URL": "https://your-project.supabase.co",
        "SUPABASE_SERVICE_ROLE_KEY": "your_service_role_key"
      }
    }
  }
}
```

> ⚠️ **Important:** Never share your secret keys publicly. The values shown above (like `sk_test_your_key_here`) are placeholders. Replace them with your real keys from each service's dashboard, and never commit them to a public GitHub repo.

### Step 3: Restart Your Tool

After saving the config file:

- **Cursor:** Close and reopen Cursor, or reload the window (`Ctrl+Shift+P` → "Reload Window")
- **Claude Desktop:** Quit the app completely and reopen it

Your AI tool needs to restart to pick up the new MCP server configuration.

### Step 4: Use It in Your Prompts

Once the MCP server is running, just talk to your AI naturally. You don't need special syntax or commands. The AI knows which tools are available and will use them when appropriate.

Try prompts like:

```
Create a new product in Stripe called "Starter Plan" at $9/month.
```

```
Show me all the tables in my Supabase database.
```

```
Look at my Figma file and build the hero section as a React component.
```

Your AI will use the MCP server behind the scenes. You'll usually see a confirmation like *"I'll use the Stripe tool to create this product"* before it acts.

---

## Real Workflow: Figma to Live Landing Page in 1 Hour

Let me walk you through a real scenario to show how MCP changes everything.

### The Goal

Sarah is building a SaaS app for freelancers to track invoices. She's designed a landing page in Figma and wants to ship it — today.

### The Old Way (Without MCP)

1. Export assets from Figma manually (30 min)
2. Recreate the layout in code by eyeballing the design (2+ hours)
3. Get the colors and spacing wrong, go back to Figma, check values, fix code (1 hour)
4. Repeat until it looks right (forever)

**Total time: 4-6 hours** (and it still doesn't match the design perfectly)

### The MCP Way

**Minute 0-5 — Setup:**
Sarah opens Cursor with the Figma MCP already configured. She pastes the link to her Figma landing page file.

```
Here's my Figma design for the InvoiceTracker landing page:
[Figma file link]

Convert the hero section into a Next.js component using Tailwind CSS.
Match the exact colors, fonts, and spacing from the design.
```

**Minute 5-15 — Hero Section:**
The AI reads the Figma file through MCP, extracts the design tokens (colors, fonts, spacing), and generates a pixel-perfect React component. Sarah previews it — it looks right.

**Minute 15-30 — Features & Pricing:**
```
Now do the features grid section and the pricing cards.
Use the same design tokens from the Figma file.
```

The AI generates both sections, consistent with the hero.

**Minute 30-45 — Stripe Integration:**
```
Create two products in Stripe:
- "Freelancer" plan at $19/month
- "Agency" plan at $49/month

Then wire up the pricing cards to link to Stripe Checkout.
```

The Stripe MCP creates the products and prices in Sarah's Stripe account. The AI generates checkout integration code and connects it to the pricing cards.

**Minute 45-60 — Polish & Deploy:**
Sarah reviews everything, tweaks a headline, and pushes to Vercel.

**Total time: 1 hour.** The landing page matches her Figma design exactly and has working payment links.

> 🎉 **That's the power of MCP.** Sarah didn't need to learn the Stripe API. She didn't need to manually export anything from Figma. She told her AI what she wanted, and the MCP servers handled the connections.

---

## Troubleshooting Common MCP Issues

MCP is powerful but it's still relatively new. Here are the issues you're most likely to run into and how to fix them.

### "MCP not connecting" / Server won't start

**What's happening:** Your AI tool can't launch the MCP server process.

**Likely causes & fixes:**

| Cause | Fix |
|---|---|
| Node.js isn't installed | MCP servers usually run on Node.js. Install it from [nodejs.org](https://nodejs.org). Pick the LTS version. |
| Wrong command in config | Double-check the `"command"` and `"args"` in your JSON. Copy them exactly from the MCP server's README. |
| Typo in the config JSON | JSON is unforgiving — one missing comma or extra bracket breaks everything. Use a [JSON validator](https://jsonlint.com/) to check your file. |
| npx can't find the package | Make sure you have internet access and the package name is spelled correctly (e.g., `@stripe/mcp`, not `stripe-mcp`). |

### "Tool not showing up" in your AI

**What's happening:** You've configured the MCP server, but your AI doesn't seem to know about it.

**Likely causes & fixes:**

- **You haven't restarted** — This is the #1 cause. Close and fully reopen your AI tool after editing the config.
- **Config file is in the wrong location** — For Cursor, it must be `.cursor/mcp.json` in your project root. For Claude Desktop, check the exact paths listed in the setup section above.
- **The MCP server crashed on startup** — Check your tool's MCP logs. In Cursor, open the Output panel and look for MCP-related messages. In Claude Desktop, check `~/Library/Logs/Claude/` (macOS) or the app's log directory.

### "Authentication error" / Invalid API key

**What's happening:** The MCP server is running, but the service (Stripe, Supabase, etc.) is rejecting the connection.

**Likely causes & fixes:**

- **Wrong key copied** — Go to the service's dashboard and re-copy the key. Make sure you're using the right one (e.g., Stripe has multiple keys — you probably want the *secret key*, not the *publishable key*).
- **Key has expired or been revoked** — Generate a new key from the service's settings.
- **Using a production key in test mode (or vice versa)** — For Stripe, keys starting with `sk_test_` are for testing. Keys starting with `sk_live_` are for production. Start with test keys while building.
- **Extra spaces or quotes in the key** — Make sure the key in your JSON doesn't have any trailing spaces or extra quote marks.

### "Server crashes" or unexpected errors

**What's happening:** The MCP server starts but then crashes during use.

**Likely causes & fixes:**

- **Rate limiting** — Some services limit how many requests you can make. Wait a minute and try again. If it keeps happening, check the service's rate limit docs.
- **Outdated MCP server** — MCP servers get updated frequently. Try running `npx clear-npx-cache` and then retry — npx will fetch the latest version.
- **Incompatible Node.js version** — Some MCP servers need Node.js 18 or later. Check your version with `node --version` in your terminal and update if needed.

> 💡 **General debugging tip:** When something isn't working, the best first step is always: read the error message, then check the MCP server's GitHub README for known issues. Most problems have a quick fix documented there.

---

## Key Takeaways

1. **MCP = Plugins for your AI.** Each MCP server connects your AI to a specific service (Stripe, Figma, Supabase, etc.).
2. **Setup is just JSON.** You add a few lines to a config file, restart your tool, and you're good to go.
3. **You don't need to learn APIs.** The MCP server handles the technical connection. You just describe what you want in plain English.
4. **Start with what you need.** Don't install every MCP server at once. Pick the 1-2 that match your current project.
5. **MCP is evolving fast.** New servers are being built every week. Check the [MCP servers directory](https://github.com/modelcontextprotocol/servers) regularly for new superpowers.

---

> **Next up:** Now that your AI has superpowers, let's talk about how to deploy your app and get it in front of real users. Onward! 🚀
