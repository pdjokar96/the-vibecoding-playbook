# Chapter 13: Agent Skills — Teaching Your AI New Tricks

You've been chatting with your AI coding assistant, and it's been doing great work. But have you noticed that sometimes it makes choices you don't love? Maybe it picks a CSS framework you've never used, or it writes code comments in a style that confuses you, or it keeps suggesting libraries when you've already picked the ones you want.

What if you could hand your AI a "cheat sheet" before every conversation — so it *already knows* your preferences without you repeating yourself?

That's exactly what **skills** (also called **custom instructions** or **rules files**) do. And the best part? They're just plain text files. No installation, no configuration wizards, no technical setup. Just words in a file. ✨

---

## What Are Skills? (The Simple Explanation)

Think of it this way:

> **Skills are like a cheat sheet you give to a new employee on their first day.** Instead of explaining your preferences every single time — "We use blue buttons, not green," "Always add error messages the user can understand," "Our app is built with Next.js" — you write them down once. Then the AI follows them automatically in every conversation.

In practice, a "skill" is just a **text file** (usually markdown) that lives in your project folder. When you open your AI coding tool, it reads that file and adjusts its behavior accordingly.

Here's what that means for you:

- ✅ You write your preferences **once**
- ✅ The AI follows them **every time** you chat
- ✅ No more repeating "use Tailwind CSS" in every prompt
- ✅ Your code stays **consistent** across your entire project
- ✅ You can share your skills with others (or use skills others have made)

It's really that simple. No magic, no complex setup — just a well-written note to your AI assistant.

---

## Where Skills Live (By Tool)

Each AI coding tool looks for its skill file in a slightly different place, but the concept is identical. Here's exactly where to put yours:

### 🟣 Cursor → `.cursorrules`

- **Filename:** `.cursorrules`
- **Location:** The root (top-level folder) of your project
- **Format:** Plain text or markdown

```
my-awesome-app/
├── .cursorrules        ← right here!
├── src/
├── package.json
└── ...
```

> 💡 **Note:** The dot at the beginning of `.cursorrules` means it's a "hidden file." Don't worry about that — just create it and Cursor will find it.

---

### 🟠 Claude Code → `CLAUDE.md`

- **Filename:** `CLAUDE.md`
- **Location:** The root of your project
- **Format:** Markdown

```
my-awesome-app/
├── CLAUDE.md           ← right here!
├── src/
├── package.json
└── ...
```

Claude Code reads this file automatically when you start a session in that project folder. You can also place a `CLAUDE.md` in your home directory for global instructions that apply to *every* project.

---

### 🔵 GitHub Copilot → `.github/copilot-instructions.md`

- **Filename:** `copilot-instructions.md`
- **Location:** Inside a `.github` folder in your project root
- **Format:** Markdown

```
my-awesome-app/
├── .github/
│   └── copilot-instructions.md  ← right here!
├── src/
├── package.json
└── ...
```

> 💡 **Tip:** If you don't already have a `.github` folder, just create one. It's a normal folder — nothing fancy about it.

---

### 🟢 Windsurf → `.windsurfrules`

- **Filename:** `.windsurfrules`
- **Location:** The root of your project
- **Format:** Plain text or markdown

```
my-awesome-app/
├── .windsurfrules      ← right here!
├── src/
├── package.json
└── ...
```

---

### The Pattern

See how similar they all are? Every tool is doing the same thing:

1. You create a text file in your project
2. You write your preferences in plain English
3. The AI reads it and follows your rules

That's it. No npm packages to install, no settings menus to navigate, no accounts to configure. Just a file with words in it.

---

## Pre-Built Skills for Solopreneurs

You don't have to write your skill file from scratch. There are ready-made skill sets designed for common needs. Here are three categories that are especially useful for solopreneurs:

### 🔒 VibeSec Skill — Security on Autopilot

Security can feel intimidating, but a VibeSec skill file handles the scary stuff for you. It tells your AI to automatically write secure code without you having to think about it.

Here's a taste of what a VibeSec skill includes:

```markdown
## Security Rules

- Never hardcode API keys, passwords, or secrets in the code. Always use
  environment variables.
- Always validate and sanitize user input before using it. Never trust data
  that comes from the user.
- Use parameterized queries for all database operations. Never build SQL
  strings by concatenating user input.
- Always set HTTP-only, secure flags on cookies.
- Add rate limiting to all API endpoints to prevent abuse.
- Never expose detailed error messages to users. Log the details server-side,
  but show the user a friendly generic message.
- Always use HTTPS URLs, never HTTP.
```

With this in place, your AI will automatically avoid common security mistakes — even if you don't know what those mistakes are yet.

---

### 🎨 UI/UX Skills — Consistent, Beautiful Design

If you've ever noticed your app looking different on every page — different button styles, inconsistent spacing, random font sizes — a UI/UX skill fixes that.

```markdown
## UI/UX Rules

- Use a consistent color palette: primary (#2563EB), secondary (#7C3AED),
  accent (#F59E0B), background (#F9FAFB), text (#111827).
- All buttons should have rounded corners (border-radius: 8px) and consistent
  padding (12px 24px).
- Always include hover and focus states for interactive elements.
- Design mobile-first: start with the mobile layout, then add tablet and
  desktop breakpoints.
- Use a minimum touch target size of 44x44 pixels for mobile buttons and links.
- Add meaningful alt text to all images for accessibility.
- Use consistent spacing: 4px, 8px, 16px, 24px, 32px, 48px, 64px scale.
- Show loading states for any action that takes more than 300ms.
- Display toast notifications for success/error feedback, not alert boxes.
```

---

### ⚙️ Framework-Specific Skills — Best Practices Built In

If you're building with a specific framework (and you probably are), there are skill sets tailored to that framework's best practices.

**Example: Next.js + React + Tailwind skill:**

```markdown
## Tech Stack Rules

- This project uses Next.js 14 with the App Router (not Pages Router).
- Use Server Components by default. Only add "use client" when the component
  needs interactivity (clicks, forms, state).
- Use Tailwind CSS for all styling. Do not write custom CSS files.
- Use TypeScript for all files. Prefer interfaces over types for object shapes.
- For data fetching, use Server Components with async/await. Avoid useEffect
  for data loading.
- Place reusable components in src/components/.
- Place page-level components in src/app/ following the App Router convention.
- Use next/image for all images to get automatic optimization.
- Use next/link for all internal navigation, never <a> tags.
```

---

## How to Create Your Own Skill File (Step by Step)

Ready to make your own? Here's exactly how to do it, no matter which tool you use.

### Step 1: Create the File

Open your project folder and create the right file for your tool:

| Tool | What to create |
|------|---------------|
| Cursor | Create a file called `.cursorrules` in your project's top folder |
| Claude Code | Create a file called `CLAUDE.md` in your project's top folder |
| GitHub Copilot | Create a folder called `.github`, then create `copilot-instructions.md` inside it |
| Windsurf | Create a file called `.windsurfrules` in your project's top folder |

> 💡 **How to create the file:** You can do this right in your code editor. In VS Code or Cursor, right-click in the file explorer sidebar → "New File" → type the filename. That's it!

### Step 2: Write Your Rules in Plain English

This is the fun part. You don't need to write code or use any special syntax. Just write clear instructions in everyday language. Think of it as writing a note to a very eager (but very literal) assistant.

**Good rules are:**
- **Specific:** "Use Tailwind CSS for styling" beats "Use good styling"
- **Actionable:** "Add a loading spinner for API calls" beats "Handle loading well"
- **Organized:** Group related rules under headings

**Format tips:**
- Use `##` headings to organize sections
- Use `-` bullet points for individual rules
- Keep each rule to one or two sentences
- Be direct — say "Do this" or "Never do that"

### Step 3: Write Your Complete Skill File

Here's a full example you can use as inspiration. This covers the most important areas for a solopreneur project:

```markdown
# Project Rules

## About This Project
- This is a SaaS web application for small business owners to manage invoices.
- The target users are non-technical. Everything should be simple and intuitive.
- We prioritize working features over perfect code.

## Tech Stack
- Frontend: Next.js 14 with App Router, React, TypeScript
- Styling: Tailwind CSS (no custom CSS files)
- Database: Supabase (PostgreSQL)
- Auth: Supabase Auth with email/password and Google OAuth
- Payments: Stripe for subscriptions
- Hosting: Vercel

## Coding Style
- Write simple, readable code. Avoid clever one-liners that are hard to understand.
- Use descriptive variable names: `invoiceTotal` not `x` or `tmp`.
- Keep functions short — if a function is longer than 30 lines, break it into
  smaller functions.
- Add a brief comment only when the "why" isn't obvious from the code itself.
- Use async/await instead of .then() chains for promises.

## Security
- Never hardcode API keys or secrets. Always use environment variables.
- Validate all user input on both client and server side.
- Use Supabase Row Level Security (RLS) policies on all tables.
- Sanitize any user-provided content before rendering it.
- Always check that the logged-in user owns the data they're requesting.

## UI/UX Conventions
- Mobile-first design. Test on small screens before desktop.
- Use the project's existing color scheme (check tailwind.config.ts).
- All forms should show inline validation errors below the field.
- Buttons should show loading state while actions are processing.
- Use toast notifications for success/error messages.
- Every page should have a clear heading that tells the user where they are.

## File Structure
- Pages go in src/app/ following Next.js App Router conventions.
- Reusable UI components go in src/components/ui/.
- Business logic components go in src/components/features/.
- Utility functions go in src/lib/utils/.
- Database queries go in src/lib/db/.
- Type definitions go in src/types/.

## Communication Style
- When explaining code changes, use simple language. Assume I'm not a developer.
- If you're about to do something complex, explain what you're doing and why
  before writing the code.
- If something could be done multiple ways, briefly explain the options and
  recommend one.
- When you encounter a bug, explain what went wrong in plain English before
  jumping into the fix.
```

### Step 4: Save and Start Using It

Just save the file. That's the entire setup.

The next time you start a conversation with your AI assistant in that project, it will automatically read your skill file and follow your rules. You don't need to restart anything or enable a setting.

> 🎯 **Pro tip:** Test it! After saving your skill file, ask your AI to "create a new button component" or "add a login page." Watch how it follows your rules — using your preferred framework, your styling approach, your file structure. It feels like magic, but it's just your cheat sheet at work.

---

## The "Project Personality" Concept

Here's a powerful way to think about skills: you're giving your project a **personality**.

Without a skill file, every conversation with your AI starts from zero. The AI might:
- Use React in one conversation and Vue in the next
- Write CSS one time and Tailwind the next
- Put files in random folders
- Use different naming conventions every session

It's like hiring a new contractor every single day who has never seen your project before. Exhausting.

With a skill file, your AI has a **consistent personality** across every conversation. It's like having a team member who:
- ✅ Knows your tech stack inside and out
- ✅ Follows your naming conventions without being reminded
- ✅ Puts files in the right place every time
- ✅ Writes code that looks like it was all written by the same person
- ✅ Remembers your security practices

This is especially important for solopreneurs because **you are the entire team.** You need consistency even more than a big team does, because there's no code review process to catch when things drift off track.

> Think of your skill file as your project's "brand guidelines" — but for code instead of design.

### Growing Your Personality Over Time

Your skill file isn't set in stone. As you build your project, you'll discover new preferences:

- "Oh, I actually like when the AI puts helper functions in a separate file"
- "I want all my API routes to follow the same error handling pattern"
- "I prefer descriptive commit messages that start with a verb"

Just open your skill file and add the new rule. It takes 10 seconds and saves you from repeating yourself for the rest of the project.

---

## Community Skill Libraries: Where to Find More

One of the coolest things about skill files is that people share them. You can browse what others have created and borrow ideas (or entire files) for your own projects.

### 📚 Where to Look

**cursor.directory**
A curated collection of `.cursorrules` files organized by framework, language, and use case. Search for your tech stack and you'll likely find a well-crafted skill file ready to go.

**awesome-cursorrules (GitHub)**
Community-maintained lists of high-quality rule files. These repos collect the best skill files from developers around the world. Search GitHub for "awesome-cursorrules" and you'll find several.

**Community Forums & Discord Servers**
The Cursor community forum, Claude Discord, and various AI coding communities frequently share and discuss skill files. Great place to find niche skills for specific use cases.

**Other Developers' Open Source Projects**
When you find an open-source project you admire, check if they have a `.cursorrules`, `CLAUDE.md`, or similar file in their repo. You can learn a lot from how experienced developers instruct their AI.

### 🔧 How to Adapt Someone Else's Rules

Found a skill file you like? Here's how to make it yours:

1. **Copy the file** into your project (rename it to match your tool's convention)
2. **Read through every rule** — do you actually agree with each one?
3. **Remove rules** that don't apply to your project (e.g., if it mentions Python but you're using JavaScript)
4. **Update specifics** like framework versions, folder paths, and tool names to match your project
5. **Add your own rules** on top — your personal preferences, your project's unique needs

> ⚠️ **Don't just blindly copy.** A skill file written for an experienced developer's enterprise project might include rules that confuse your AI when applied to your solopreneur app. Keep it relevant to YOUR project and YOUR skill level.

---

## Template: Starter Skill File for Solopreneurs

Here's a complete, ready-to-use skill file template. Copy this into your project's skill file (`.cursorrules`, `CLAUDE.md`, `.github/copilot-instructions.md`, or `.windsurfrules`), then customize the bracketed `[placeholders]` to match your project.

```markdown
# [Your Project Name] — AI Coding Rules

## Project Overview
- This is a [type of app, e.g., "SaaS web app" or "mobile-friendly web tool"].
- Purpose: [one sentence describing what the app does].
- Target users: [who uses it, e.g., "freelancers who need simple invoicing"].
- I am a solopreneur with limited coding experience. Keep things simple.

## Tech Stack (Do Not Deviate)
- Framework: [e.g., Next.js 14 with App Router]
- Language: [e.g., TypeScript]
- Styling: [e.g., Tailwind CSS]
- Database: [e.g., Supabase]
- Authentication: [e.g., Supabase Auth]
- Hosting: [e.g., Vercel]
- Payments: [e.g., Stripe] (if applicable)

## Coding Conventions
- Write simple, readable code. Avoid unnecessary complexity.
- Use descriptive names for variables and functions (e.g., `calculateTotal`
  not `calc` or `x`).
- Keep functions focused on one task and under 30 lines when possible.
- Use async/await for all asynchronous operations.
- Handle errors gracefully — always use try/catch blocks around API calls
  and database queries.
- Prefer named exports over default exports.

## Security (Non-Negotiable)
- Never hardcode secrets, API keys, or passwords. Use environment variables.
- Validate and sanitize ALL user input on both client and server.
- Always check user authentication before serving protected content.
- Always check that users can only access their own data (authorization).
- Use HTTPS for all external API calls.
- Never log sensitive user data (passwords, tokens, personal info).

## UI/UX Standards
- Design mobile-first, then scale up to tablet and desktop.
- Use consistent spacing based on a 4px/8px grid.
- All interactive elements (buttons, links) must have hover and focus states.
- Show loading indicators for any operation that may take time.
- Display user-friendly error messages — no technical jargon.
- Forms should validate inline and show errors next to the relevant field.
- Use toast notifications for action confirmations (not alert boxes).
- Ensure text contrast meets accessibility standards (WCAG AA minimum).

## File & Folder Structure
- Pages/routes: [e.g., src/app/]
- Reusable UI components: [e.g., src/components/ui/]
- Feature-specific components: [e.g., src/components/features/]
- Utility/helper functions: [e.g., src/lib/utils/]
- Database queries/logic: [e.g., src/lib/db/]
- Type definitions: [e.g., src/types/]
- API route handlers: [e.g., src/app/api/]

## Communication Preferences
- Explain changes in plain, simple language. Assume I'm not a professional
  developer.
- When there are multiple approaches, recommend one and briefly explain why.
- If something is risky or could break existing features, warn me before
  making the change.
- After making changes, give me a short summary of what was done and how
  to test it.
- If I ask for something that's a bad practice, gently explain why and
  suggest a better alternative.

## Project-Specific Rules
- [Add any rules unique to your project here]
- [e.g., "All prices should be displayed in USD with two decimal places"]
- [e.g., "The app supports English only for now"]
- [e.g., "Use the company logo from public/logo.svg in the header"]
```

> 🚀 **How to use this template:**
> 1. Copy everything inside the code block above
> 2. Create the right file for your tool (see the "Where Skills Live" section)
> 3. Paste it in
> 4. Replace every `[placeholder]` with your actual project details
> 5. Delete any sections that don't apply
> 6. Add your own rules at the bottom
> 7. Save — you're done!

---

## Quick Recap

| What | Why It Matters |
|------|---------------|
| Skill files are plain text | No technical setup required — just write and save |
| Every tool has its own filename | `.cursorrules`, `CLAUDE.md`, `copilot-instructions.md`, `.windsurfrules` |
| Write rules in plain English | No special syntax, no programming knowledge needed |
| Pre-built skills exist | Security, UI/UX, and framework skills are ready to copy |
| Your project gets a "personality" | Consistent code across every AI conversation |
| Community libraries are free | Browse cursor.directory and GitHub for inspiration |
| Start with the template | Customize it as you learn what works for your project |

The beauty of skill files is that they grow with you. Start with the template above, and every time you think "I wish the AI would do X differently," just add a new rule. Over time, your skill file becomes a perfect reflection of how *you* want your project built.

You're not just coding — you're training your AI to think like your ideal team member. 🎯

---

**Next up:** [Chapter 14 — The Solopreneur Workflow](../14-solopreneur-workflow/README.md) — putting all these pieces together into a daily workflow that actually ships products.
