# Chapter 2: Choosing Your Tools 🧰

[← Previous: What Is Vibe Coding?](../01-what-is-vibe-coding/) · [Back to Playbook](../../README.md) · [Next: Your First App →](../03-first-app/)

---

## Why Tool Choice Matters

Before you build anything, you need to pick your workspace. Think of it like cooking — you *could* make a meal in any kitchen, but the right setup makes it easier, faster, and more fun.

The good news: there's no wrong choice. Every tool we cover in this chapter can help you build real apps. The *best* choice depends on your comfort level, your goals, and how much control you want over the process.

Let's break down the landscape.

---

## The Three Categories of Vibe Coding Tools

All vibe coding tools fall into three categories. Think of them as three levels of a kitchen:

### 🟢 Category 1: Vibe-First Platforms (No Installation Needed)

**What they are:** Web-based tools where you describe your app in a text box, and the platform builds it — complete with a visual preview, editable code, and one-click deployment. You don't install anything. You don't touch a terminal. Everything happens in your browser.

**Best for:** Complete beginners, rapid prototyping, getting your first app live fast.

**Examples:**
- **Lovable** (lovable.dev) — Describe your app, see it built in real-time, deploy with one click
- **Bolt** (bolt.new) — Similar to Lovable, very fast, great for quick prototypes
- **v0** (v0.dev) — By Vercel, excellent for generating UI components and pages
- **Replit Agent** (replit.com) — Full development environment in the browser with an AI agent that builds for you

**The analogy:** These are like meal kit delivery services. Everything comes pre-measured and ready to go. You just follow the steps and end up with a great meal.

---

### 🟡 Category 2: AI-Powered IDEs (More Control)

**What they are:** Desktop applications that look like a professional code editor, but with AI built right in. You open a chat panel, describe what you want, and AI writes the code directly into your project files. You get more control over the project structure, can install additional tools, and can customize everything.

**Best for:** People who want more control, plan to build multiple apps, or want to learn more about how things work under the hood.

**Examples:**
- **Cursor** (cursor.com) — The most popular AI-powered IDE, built on top of VS Code
- **Windsurf** (windsurf.com) — AI-first editor with strong autonomous capabilities
- **GitHub Copilot in VS Code** (code.visualstudio.com) — Microsoft's AI coding assistant inside VS Code

**The analogy:** These are like having a professional kitchen with a sous chef. You have all the tools, and a skilled helper standing beside you. You direct the cooking, but you have more freedom to experiment.

---

### 🔵 Category 3: AI Assistants (Chat-Based)

**What they are:** Chat interfaces where you can ask AI for code, explanations, debugging help, and advice. They don't build the app *for* you directly — they give you code that you then copy into your project. Think of them as incredibly knowledgeable advisors.

**Best for:** Getting explanations, brainstorming ideas, understanding code that other tools generated, troubleshooting problems.

**Examples:**
- **Claude** (claude.ai) — By Anthropic, excellent at reasoning and generating high-quality code
- **ChatGPT** (chat.openai.com) — By OpenAI, the most well-known AI assistant
- **Gemini** (gemini.google.com) — By Google, strong at multi-modal tasks (text + images)

**The analogy:** These are like calling a master chef for advice. They'll tell you exactly what to do, step by step, but you're the one doing the cooking.

---

## Comparison Table

Here's a side-by-side comparison to help you decide:

| Tool | Category | Free Tier? | Best For | Learning Curve | Deploy Built-in? |
|------|----------|-----------|----------|---------------|-----------------|
| **Lovable** | Vibe-first platform | ✅ Yes (limited) | First apps, landing pages, MVPs | 🟢 Very easy | ✅ Yes |
| **Bolt** | Vibe-first platform | ✅ Yes (limited) | Quick prototypes, small apps | 🟢 Very easy | ✅ Yes |
| **v0** | Vibe-first platform | ✅ Yes (limited) | UI components, page designs | 🟢 Very easy | ✅ Yes (via Vercel) |
| **Replit Agent** | Vibe-first platform | ✅ Yes (limited) | Full apps, learning to code | 🟢 Easy | ✅ Yes |
| **Cursor** | AI-powered IDE | ✅ Yes (limited) | Serious projects, full control | 🟡 Moderate | ❌ No (use Vercel/Netlify) |
| **Windsurf** | AI-powered IDE | ✅ Yes (limited) | Autonomous building, exploring | 🟡 Moderate | ❌ No (use Vercel/Netlify) |
| **GitHub Copilot** | AI-powered IDE | ✅ Yes (free plan) | VS Code users, code completion | 🟡 Moderate | ❌ No (use Vercel/Netlify) |
| **Claude** | AI assistant | ✅ Yes (limited) | Brainstorming, explanations, debugging | 🟢 Easy | ❌ No |
| **ChatGPT** | AI assistant | ✅ Yes (limited) | General questions, code snippets | 🟢 Easy | ❌ No |
| **Gemini** | AI assistant | ✅ Yes | Research, multi-modal tasks | 🟢 Easy | ❌ No |

> 💡 **"Limited" free tier** means you can use it for free, but there's a cap on how many prompts or projects you can run per day/month. For serious building, you'll likely want a paid plan ($10–$25/month for most tools).

---

## Which Should I Pick? A Decision Guide

Not sure where to start? Walk through this decision tree:

```
START HERE
│
├─ "I want to build something RIGHT NOW without installing anything"
│   │
│   ├─ "I want a full app (pages, database, auth)"
│   │   └─ → Use Lovable or Bolt
│   │
│   └─ "I just want a beautiful UI component or page"
│       └─ → Use v0
│
├─ "I want more control and plan to build multiple projects"
│   │
│   ├─ "I'm okay installing a desktop app"
│   │   └─ → Use Cursor (most popular) or Windsurf
│   │
│   └─ "I want everything in the browser still"
│       └─ → Use Replit Agent
│
└─ "I just want to ask questions and get advice"
    │
    ├─ "I want the best code quality and reasoning"
    │   └─ → Use Claude
    │
    └─ "I want a general-purpose AI helper"
        └─ → Use ChatGPT or Gemini
```

**Still can't decide?** Here's the simplest advice:

> 🎯 **Start with Lovable or Bolt for your first app.** Once you're comfortable, **graduate to Cursor** for more control and bigger projects. Use **Claude or ChatGPT** alongside either tool for brainstorming and debugging.

---

## Setting Up Each Tool

Here's a quick guide to getting started with the most popular options. Each tool has excellent official documentation — we'll link to it and focus on the "just get me started" steps.

---

### 🟢 Setting Up Lovable

**Time to set up:** 2 minutes

1. **Go to** [lovable.dev](https://lovable.dev)
2. **Sign up** with your Google or GitHub account (both are free to create)
3. **Click "New Project"**
4. **Describe your app** in the text box — for example: *"Build me a personal portfolio website with a hero section, about me, project gallery, and a contact form"*
5. **Watch Lovable build it** in real-time (this usually takes 30–60 seconds)
6. **Iterate** by typing follow-up instructions: *"Make the header sticky"* or *"Change the color scheme to dark blue and white"*
7. **Deploy** with the "Publish" button when you're happy

📖 [Lovable Official Docs](https://docs.lovable.dev)

---

### 🟢 Setting Up Bolt

**Time to set up:** 2 minutes

1. **Go to** [bolt.new](https://bolt.new)
2. **Sign up** for a free account
3. **Describe your app** in the prompt box
4. **Bolt will generate** the full app — you'll see a live preview and the code side-by-side
5. **Chat with Bolt** to make changes
6. **Deploy** directly from the interface

📖 [Bolt Official Docs](https://docs.bolt.new)

---

### 🟡 Setting Up Cursor

**Time to set up:** 10 minutes

1. **Go to** [cursor.com](https://cursor.com) and download the app for your operating system (Windows, Mac, or Linux)
2. **Install it** like any normal application
3. **Open Cursor** — it will look like a code editor with a dark interface. Don't be intimidated! You'll mostly use the chat panel.
4. **Sign in** to activate the free tier (or enter your Pro subscription)
5. **Create a new folder** for your project (File → Open Folder → make a new folder called "my-first-app")
6. **Open the AI chat** by pressing `Ctrl+L` (Windows) or `Cmd+L` (Mac)
7. **Describe what you want:** *"Create a personal portfolio website using React and Tailwind CSS. Include a hero section, about page, projects gallery, and contact form."*
8. **Cursor will generate files** directly in your project. Review them and ask for changes.

📖 [Cursor Official Docs](https://docs.cursor.com)

> 💡 **Tip for beginners:** Cursor can feel overwhelming at first because it shows you the actual code files. Don't worry about reading the code — just focus on the chat panel and the live preview.

---

### 🟡 Setting Up Windsurf

**Time to set up:** 10 minutes

1. **Go to** [windsurf.com](https://windsurf.com) and download the editor
2. **Install and open it**
3. **Create a new project** folder
4. **Use the AI panel** (called "Cascade") to describe your app
5. **Windsurf will autonomously** create files, install dependencies, and set things up
6. **Review and iterate** by chatting with Cascade

📖 [Windsurf Official Docs](https://docs.windsurf.com)

---

### 🟡 Setting Up GitHub Copilot in VS Code

**Time to set up:** 15 minutes

1. **Download VS Code** from [code.visualstudio.com](https://code.visualstudio.com) (free)
2. **Install the GitHub Copilot extension:** Go to Extensions (the square icon on the left sidebar), search "GitHub Copilot", and click Install
3. **Sign in** with your GitHub account (create one at [github.com](https://github.com) if you don't have one — it's free)
4. **Activate Copilot:** The free plan includes code completions and chat
5. **Open the Copilot Chat panel** from the sidebar
6. **Start describing what you want to build**

📖 [GitHub Copilot Docs](https://docs.github.com/en/copilot)

---

### 🔵 Using Claude, ChatGPT, or Gemini

These don't require any setup — just go to the website and start chatting:

- **Claude:** [claude.ai](https://claude.ai)
- **ChatGPT:** [chat.openai.com](https://chat.openai.com)
- **Gemini:** [gemini.google.com](https://gemini.google.com)

**How to use them for vibe coding:**
1. Describe the feature or app you want to build
2. Ask for the complete code
3. Copy the code into your project (or into Cursor/VS Code)
4. Ask follow-up questions if something doesn't work

> 💡 **Pro tip:** These chat tools are best used **alongside** a vibe-first platform or IDE, not as replacements. Use them for brainstorming, explaining errors, and getting advice.

---

## Our Recommendation

If you're brand new and reading this playbook from the beginning, here's the path we recommend:

### Phase 1: Your First App (Chapters 1–3)
Use **Lovable** or **Bolt**. Zero setup, zero friction. Just describe and build.

### Phase 2: Getting Serious (Chapters 4–9)
Graduate to **Cursor**. You'll have more control, can build bigger apps, and will start to understand the project structure.

### Phase 3: Going Pro (Chapters 10–19)
Keep using **Cursor** as your primary tool, with **Claude** or **ChatGPT** as your brainstorming and debugging sidekick. Layer in **MCP servers** (Chapter 12) to supercharge your workflow.

**You can always switch tools.** Nothing locks you in. The skills you learn — writing good prompts, thinking in features, iterating on feedback — transfer across every tool.

---

## A Note on Costs

Let's talk money. Here's what you can expect:

| Stage | Tools | Monthly Cost |
|-------|-------|-------------|
| **Getting started** | Free tiers of Lovable/Bolt + free Claude/ChatGPT | **$0** |
| **Building seriously** | Cursor Pro + Claude Pro | **$20–$40/month** |
| **Running an app** | Hosting (Vercel/Netlify free tier) + Database (Supabase free tier) | **$0–$25/month** |

For context, hiring a freelance developer for a simple app costs **$3,000–$15,000**. A monthly SaaS subscription to build it yourself is a **fraction** of that.

---

## What's Next?

You now know the landscape of vibe coding tools and have a recommendation for where to start. In the next chapter, we're going to stop talking and **start building**. You'll create your first app in 30 minutes — for real.

No more theory. Let's get our hands dirty.

---

[← Previous: What Is Vibe Coding?](../01-what-is-vibe-coding/) · [Back to Playbook](../../README.md) · [Next: Your First App →](../03-first-app/)
