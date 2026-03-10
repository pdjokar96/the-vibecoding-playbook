# Chapter 6: Context Engineering for Beginners

> "An AI without context is like a brilliant consultant who shows up to your meeting with amnesia."

So far you've learned how to write great prompts and plan your app with a PRD. But there's a sneaky problem that trips up every vibe coder eventually:

**The AI forgets everything between conversations.**

You spend an hour building a feature, close the chat, open a new one the next morning, and… the AI has no idea what your app is, what tech stack you're using, or what you built yesterday. It's like starting from scratch every single time.

This chapter is about solving that problem. Welcome to **context engineering** — the art of making sure your AI always knows what's going on.

---

## The Problem: AI Has No Long-Term Memory

Here's something that surprises most beginners: AI doesn't remember you.

When you start a new conversation with ChatGPT, Claude, or any AI coding assistant, it begins with a completely blank slate. It doesn't remember:

- What app you're building
- What tech stack you chose
- What features you've already completed
- What decisions you made and why
- What bugs you fixed yesterday

Think of it like this: imagine you hire a brilliant freelance developer, but every morning they wake up with total amnesia. They're just as talented as yesterday, but they have zero memory of your project. Before they can help you, you'd need to brief them all over again.

That's exactly what's happening every time you start a new AI conversation.

**Context engineering is the briefing.** It's how you bring the AI up to speed quickly so it can jump right in and help.

---

## What Is "Context," Anyway?

In AI terms, **context** is everything the AI knows about your situation right now. Think of it as the AI's working memory — the information it's holding in its head during your conversation.

Context includes:
- The messages you've sent in the current conversation
- Any code you've pasted or files you've shared
- Any instructions or rules the tool has loaded automatically
- The AI's own responses (it can read back what it already said)

Context does **not** include:
- Previous conversations (unless a tool explicitly saves them)
- Your files on your computer (unless you share them)
- What you're thinking but haven't typed

The big insight: **you control the context.** The more relevant information you give the AI, the better it performs. Too little context and it guesses. Too much irrelevant context and it gets confused. The sweet spot is giving it exactly what it needs — no more, no less.

---

## The "Breadcrumb Trail" Technique 🍞

Imagine walking through a forest. If you don't leave any trail, you'll get lost trying to find your way back. But if you drop breadcrumbs, you can always retrace your steps.

Context engineering is about leaving breadcrumbs for your AI to find.

These breadcrumbs are **files in your project** that contain important information about what you're building, what decisions you've made, and how things should work. When you (or your AI tool) can reference these files, the AI gets caught up instantly.

The three types of breadcrumbs you'll use:

1. **Project rules files** — Automatic instructions that your AI tool reads every time
2. **Memory files** — Running logs of decisions and progress
3. **The context sandwich** — A prompting technique for conversations

Let's dive into each one.

---

## Project Rules Files: Automatic Context

This is the most powerful tool in your context engineering toolkit. Most AI coding assistants support a special file that they **automatically read** at the start of every conversation. It's like pinning a note to the AI's forehead that says "READ THIS FIRST."

Different tools use different file names:

| Tool | Rules File | Where to Put It |
|------|-----------|-----------------|
| **Cursor** | `.cursorrules` | Root of your project folder |
| **Claude Code** | `CLAUDE.md` | Root of your project folder |
| **GitHub Copilot** | `.github/copilot-instructions.md` | Inside a `.github` folder |
| **Windsurf** | `.windsurfrules` | Root of your project folder |

The contents of these files are nearly identical — only the filename and location differ. You can even maintain one master version and copy it to multiple files if you use more than one tool.

### What to Put in Your Rules File

Here's the information that makes the biggest difference:

#### 1. Project Overview
Tell the AI what it's working on in 2-3 sentences.

```markdown
## Project Overview
TaskFlow is a simple task manager for freelancers. It helps users
track client projects and deadlines in one clean interface. Built
as a web app, designed for simplicity over features.
```

#### 2. Tech Stack
List every major technology so the AI doesn't have to guess.

```markdown
## Tech Stack
- Framework: Next.js 14 (App Router)
- Styling: Tailwind CSS
- Database: Supabase (PostgreSQL)
- Authentication: Supabase Auth
- Hosting: Vercel
- Language: TypeScript
```

#### 3. Project Structure
Give the AI a map of where things live.

```markdown
## Project Structure
- `/app` — Pages and routes (Next.js App Router)
- `/components` — Reusable UI components
- `/lib` — Utility functions and Supabase client
- `/types` — TypeScript type definitions
```

#### 4. Coding Style & Conventions
Tell the AI how you want your code to look.

```markdown
## Coding Conventions
- Use functional components with hooks (no class components)
- Use Tailwind CSS for all styling — no separate CSS files
- Name files in kebab-case (e.g., task-card.tsx)
- Keep components small — one component per file
- Use descriptive variable names, not abbreviations
```

#### 5. Do's and Don'ts
Explicit rules prevent common mistakes.

```markdown
## Do's
- Always handle loading and error states in UI components
- Use Supabase Row Level Security for data access
- Write responsive layouts — mobile-first
- Add helpful comments for complex logic

## Don'ts
- Don't install new packages without asking first
- Don't use inline styles — use Tailwind classes instead
- Don't store sensitive data in client-side code
- Don't create separate CSS/SCSS files
```

When your AI tool reads this file automatically, every conversation starts with the AI already knowing your project, your tech stack, and your preferences. No more explaining from scratch.

---

## Memory Files: Your Project's Diary 📔

Rules files cover the "what" and "how" of your project. Memory files cover the "why" and "when" — they're a running record of decisions, changes, and progress.

### DECISIONS.md

This is a log of important decisions and the reasoning behind them. Future-you (and the AI) will thank you for this.

```markdown
# Decision Log

## 2024-01-15: Chose Supabase over Firebase
- Supabase has a more generous free tier
- PostgreSQL gives us more flexibility than Firestore
- Built-in auth that's simpler to set up
- Better for SQL-based queries, which this app will need

## 2024-01-16: Using App Router instead of Pages Router
- App Router is the future of Next.js
- Better support for server components
- Layouts and loading states are easier to implement

## 2024-01-18: No dark mode for MVP
- Adds complexity to every component
- Can be added in v2
- Most reference sites we like use light mode

## 2024-01-20: Switched from date-fns to day.js
- date-fns was adding too much to the bundle size
- day.js has a smaller footprint and covers our needs
- Only using it for date formatting and "time ago" displays
```

**When to update it:** Any time you or the AI makes a significant choice — picking a library, changing an approach, dropping a feature — write it down with the reason.

**How it helps:** When you start a new conversation, you can paste relevant decisions to give the AI context. Or better yet, reference the file: "Check DECISIONS.md for context on our tech choices."

### PROGRESS.md

A simple log of what's been built and what's left.

```markdown
# Progress Log

## Completed ✅
- [x] Project setup with Next.js, Tailwind, Supabase
- [x] Authentication (signup, login, logout)
- [x] Database schema for tasks and projects
- [x] Dashboard page showing tasks due today
- [x] Add/edit/delete tasks

## In Progress 🔧
- [ ] Project view — click a project to see its tasks
- [ ] Color-coded project labels

## Up Next 📋
- [ ] Task filtering (by project, by due date)
- [ ] Mark tasks as complete with animation
- [ ] Responsive design pass (mobile)

## Known Issues 🐛
- Task due dates display in UTC instead of local timezone
- Long project names overflow the sidebar on small screens
```

**When to update it:** At the end of each building session, spend 2 minutes updating what you finished and what's next.

**How it helps:** When you start a new conversation, paste the relevant section so the AI knows where you left off. "I've completed everything in the 'Completed' section. Now I want to work on the first item in 'In Progress'."

---

## The "Context Sandwich" Technique 🥪

When you start a new conversation with an AI (or when your rules file isn't available), use the context sandwich. It's a three-part prompt structure:

### The Top Slice: Project Summary

Start your conversation by giving the AI the essential context.

```
I'm building TaskFlow, a task manager for freelancers, using Next.js,
Tailwind CSS, and Supabase. The app lets users create projects, add
tasks with due dates, and see a dashboard of upcoming work.

So far I've built: authentication, the dashboard page, and the ability
to add/edit/delete tasks. The database has tables for `users`,
`projects`, and `tasks`.
```

### The Filling: Your Specific Request

Now make your actual request.

```
I need to add a "project view" page. When a user clicks on a project
name in the sidebar, it should show:
- The project name and color at the top
- All tasks belonging to that project, sorted by due date
- A button to add a new task directly to this project
```

### The Bottom Slice: Constraints and Reminders

End with any constraints or reminders the AI should keep in mind.

```
Remember:
- Use Tailwind CSS for styling, no separate CSS files
- The page should be responsive (mobile-friendly)
- Follow the existing code patterns in the project
- Don't install any new packages
```

Put it all together, and you get a prompt that gives the AI full context, a clear task, and important constraints — even in a brand new conversation.

### Why a Sandwich?

The reason this works so well is that AI pays special attention to the **beginning** and **end** of your messages. By putting the project context first and constraints last, you're placing the most important information where the AI is most likely to remember and follow it.

The specific request goes in the middle because the AI will focus on it as the main task, sandwiched between the context it needs to do the job right.

---

## When Context Gets Too Long

Here's a reality of AI tools: they have a **context window** — a maximum amount of text they can hold in memory at once. Think of it like the AI's working desk. It can only have so many documents spread out before things start falling off the edge.

When your conversations get really long (hundreds of messages), the AI might start:
- Forgetting things you said earlier
- Contradicting previous decisions
- Getting confused about which version of the code is current

### Signs You Need a Fresh Start

- The AI starts suggesting changes that conflict with what you already built
- It keeps "forgetting" a decision you made 50 messages ago
- Responses are getting slower or less accurate
- You're spending more time correcting the AI than building

### How to Start Fresh Without Losing Progress

Starting a new conversation doesn't mean starting over. Here's the process:

1. **Update your memory files** (PROGRESS.md, DECISIONS.md) with the latest state
2. **Update your rules file** if anything has changed
3. **Start a new conversation**
4. **Use the context sandwich** to bring the AI up to speed
5. **Continue building** from where you left off

It takes about 2 minutes to set up a fresh conversation this way, and the AI will be just as effective as if it had been there the whole time.

### Pro Tip: Save Good Conversations

If an AI conversation was particularly productive — maybe you solved a tricky problem or made an important architectural decision — save the key parts. You can:

- Copy the important messages into your DECISIONS.md
- Save the final code in your project
- Write a brief summary of what was accomplished

Think of it as taking notes after a meeting. The meeting is over, but the notes remain.

---

## Template: A Starter Project Rules File

Here's a complete, ready-to-use template. Copy it, fill in the blanks, and save it as the appropriate file for your tool.

```markdown
# Project Rules

## Overview
[Your app name] is a [type of app] that helps [target user] to
[core benefit]. It's built as a [web app / mobile app / etc.].

## Tech Stack
- Framework: [e.g., Next.js 14]
- Language: [e.g., TypeScript]
- Styling: [e.g., Tailwind CSS]
- Database: [e.g., Supabase]
- Authentication: [e.g., Supabase Auth]
- Hosting: [e.g., Vercel]

## Project Structure
- `/app` — [what lives here]
- `/components` — [what lives here]
- `/lib` — [what lives here]
- `/public` — [static assets like images]

## Current State
[Brief description of what has been built so far. Update this as
you make progress.]

## Key Decisions
[List 2-3 important architectural or design decisions. Link to
DECISIONS.md for the full log.]

## Coding Style
- [Convention 1, e.g., "Use functional components"]
- [Convention 2, e.g., "Use Tailwind, no CSS files"]
- [Convention 3, e.g., "Kebab-case file names"]
- [Convention 4, e.g., "Small, focused components"]

## Do's
- Handle loading and error states in all UI components
- Write responsive, mobile-first layouts
- Keep components small and single-purpose
- Use meaningful variable and function names

## Don'ts
- Don't add new npm packages without mentioning it first
- Don't use inline styles — use Tailwind
- Don't put API keys or secrets in client-side code
- Don't create large, monolithic components

## AI Instructions
When generating code for this project:
1. Follow the existing patterns and style in the codebase
2. Add brief comments explaining non-obvious logic
3. Always include error handling
4. Make UI responsive by default
5. If unsure about a decision, ask before implementing
```

Save this as:
- `.cursorrules` if you use Cursor
- `CLAUDE.md` if you use Claude Code
- `.github/copilot-instructions.md` if you use GitHub Copilot
- `.windsurfrules` if you use Windsurf

---

## Putting It All Together: A Daily Workflow

Here's what context engineering looks like in practice, day to day:

### When You Start a New Project
1. Fill out the project rules file template (10 minutes)
2. Create empty DECISIONS.md and PROGRESS.md files
3. Save your PRD (from Chapter 5) in the project folder

### When You Start a Building Session
1. Open your AI tool — the rules file loads automatically
2. If starting a new conversation, use the context sandwich
3. Reference PROGRESS.md to remind the AI where you left off
4. Start building!

### When You Finish a Building Session
1. Update PROGRESS.md with what you completed
2. Add any new decisions to DECISIONS.md
3. Update the rules file if the project structure or stack changed
4. Save your work (commit to Git if you're using it)

### When Context Gets Stale
1. Update your memory files
2. Start a fresh conversation
3. Use the context sandwich to set up the new conversation
4. Keep building without missing a beat

This routine takes maybe 5 extra minutes per session, but it makes every conversation with the AI dramatically more productive.

---

## Quick Reference: Context Engineering Cheat Sheet

| Situation | What to Do |
|-----------|-----------|
| Starting a new project | Create a rules file + DECISIONS.md + PROGRESS.md |
| Starting a new conversation | Use the context sandwich technique |
| AI forgot something important | Paste the relevant section from your memory files |
| AI contradicts earlier decisions | Reference DECISIONS.md |
| Conversation is getting too long | Start fresh — update files, new conversation |
| Switched AI tools | Copy your rules file with the new tool's filename |
| Project structure changed | Update the rules file immediately |
| Made an important decision | Log it in DECISIONS.md with the "why" |
| Finished a feature | Update PROGRESS.md |

---

## Key Takeaways

1. **AI has no memory between conversations.** You need to bring the context every time.
2. **Project rules files are your best friend.** They load automatically and give the AI instant context about your project.
3. **Memory files (DECISIONS.md, PROGRESS.md) are your project diary.** They capture what you've built and why, so you never lose track.
4. **The context sandwich (summary → request → constraints)** is the go-to structure for starting productive conversations.
5. **Starting fresh is healthy.** When conversations get long, don't be afraid to start a new one — just bring your breadcrumbs.
6. **5 minutes of context management saves hours of frustration.** It's the highest-leverage habit you can build.

---

## What's Next?

You now have the core skills of vibe coding: prompting, planning, and context management. In the next chapter, we'll put it all together and learn how to **build iteratively** — turning your PRD into a working app, one small step at a time.

[→ Chapter 7: Building Iteratively](../07-building-iteratively/README.md)
