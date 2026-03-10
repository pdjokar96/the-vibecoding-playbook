# Chapter 17: Patterns That Work (and Anti-Patterns That Don't) 🧩

After watching hundreds of people build apps with AI, clear patterns emerge. Some habits lead to smooth, enjoyable building. Others lead to frustration, wasted hours, and broken apps.

This chapter is your cheat sheet. The patterns are habits to adopt. The anti-patterns are traps to avoid. Bookmark this page — you'll want to revisit it when you feel stuck.

---

## ✅ Pattern 1: "UI First" — Start with How It Looks, Add Logic Later

### The Pattern

Build the visual part of your app first — the screens, buttons, forms, and layout — before adding any real functionality behind it.

### Why It Works

Imagine you're designing a house. You wouldn't start by wiring the electricity — you'd start with the floor plan. You want to see the rooms, the windows, the doors. *Then* you add plumbing and electrical.

Building UI first gives you:
- **Quick visual progress** — you can see your app taking shape in minutes, which keeps you motivated
- **Better conversations with AI** — you can screenshot your UI and say "now make this button actually work"
- **Easier feedback** — you can show people your app before it's functional and get early input on the design

### How to Do It

1. Start by asking AI to create the screens of your app with placeholder data
2. Get the layout and design right
3. Then go screen by screen, adding real functionality

### Example Prompt

> *"Create a dashboard page for a fitness tracking app. Include a header with the app name, a sidebar with navigation links (Dashboard, Workouts, Progress, Settings), and a main area showing 4 stat cards (Total Workouts, Calories Burned, Streak Days, Next Workout). Use placeholder data for now — we'll add real data later."*

---

## ✅ Pattern 2: "One Feature Per Conversation" — Keep AI Focused

### The Pattern

When building features, dedicate one conversation (or one focused session) to one feature. Don't try to build your login system, payment processing, and dashboard all in the same conversation.

### Why It Works

AI assistants have a context window — think of it as their working memory. The more you pile into a single conversation, the more likely the AI is to:
- Forget earlier decisions
- Introduce contradictions
- Make mistakes in areas you already finished

By keeping conversations focused, you get higher-quality code and fewer bugs.

### How to Do It

1. **Conversation 1**: Build the user registration and login flow
2. **Conversation 2**: Build the main dashboard
3. **Conversation 3**: Build the settings page
4. **Conversation 4**: Add payment processing

At the start of each new conversation, give the AI context about what already exists:

> *"I'm building a fitness app. I already have user authentication and a dashboard. Here's my current project structure: [paste]. Now I want to add a workout logging feature."*

### When to Start a New Conversation

- When you're moving to a clearly different feature
- When the conversation is getting really long (50+ messages)
- When the AI starts making mistakes or forgetting things
- After completing and testing a feature successfully

---

## ✅ Pattern 3: "Spec-Driven Development" — Write a Mini-Spec Before Each Feature

### The Pattern

Before asking AI to build something, spend 5 minutes writing down exactly what you want. Not code — just plain English describing the feature.

### Why It Works

The #1 reason people get frustrated with AI coding is vague prompts. "Build me a login page" can be interpreted a hundred different ways. But a mini-spec removes ambiguity:

> Instead of: *"Build me a login page"*
>
> Write: *"Build a login page with:
> - Email and password fields
> - A 'Remember me' checkbox
> - A 'Forgot password?' link (goes to /forgot-password)
> - A 'Sign up' link at the bottom (goes to /signup)
> - Show error message below the form if login fails
> - Redirect to /dashboard on successful login
> - Use the same styling as our existing signup page"*

### How to Do It

For each feature, answer these questions:
1. **What does the user see?** (Screens, forms, buttons)
2. **What does the user do?** (Clicks, types, drags)
3. **What happens when they do it?** (Data saved, page changes, notification appears)
4. **What can go wrong?** (Invalid input, network error, not logged in)
5. **What does success look like?** (Confirmation message, redirect, email sent)

> 💡 Use our [PRD Template](../../templates/prd-template.md) for a structured way to write specs!

---

## ✅ Pattern 4: "Screenshot Prompting" — Use Screenshots and Mockups as Inputs

### The Pattern

When you want AI to build something that looks a certain way, show it a picture. A screenshot or mockup is worth a thousand words of description.

### Why It Works

Describing visual designs in words is hard. "I want a card with rounded corners, a shadow, the title on the left, and a small icon on the right" — that could look like a hundred different things. But a screenshot? That's crystal clear.

### How to Do It

1. **Screenshot an app you like**: See a pricing page you love? Screenshot it
2. **Sketch on paper and photograph it**: Even rough drawings help
3. **Use a simple mockup tool**: Tools like Excalidraw (free) let you sketch layouts quickly
4. **Screenshot your current app**: "Make this page look like this design"

### Example Prompt

> *"I want my pricing page to look similar to the attached screenshot. I need three tiers: Free, Pro ($19/month), and Team ($49/month). Keep the same general layout — cards side by side, the Pro tier highlighted, feature lists under each tier."*

Most AI tools (ChatGPT, Claude, etc.) can accept images directly in the conversation. Use this power!

---

## ✅ Pattern 5: "The Undo Safety Net" — Always Commit Before Big Changes

### The Pattern

Before making any significant change to your app, create a Git commit. This gives you a save point you can return to if things go wrong.

### Why It Works

Think of it like saving your game before a boss fight. If the boss beats you, you can reload your save and try again. Without that save point, you'd have to start the whole game over.

In coding terms: if AI makes a change that breaks everything, you can undo it instantly instead of trying to manually figure out what went wrong.

### How to Do It

Before starting any new feature or significant change:

```bash
git add .
git commit -m "Save point: everything working before adding [feature]"
```

If things go wrong:
```bash
git stash          # Temporarily set aside your changes
# Test if the app works again
git stash pop      # Bring changes back if you want them
# OR
git checkout .     # Throw away all changes since last commit
```

### The Golden Rule

> **Commit when things work. Never commit when things are broken.**

This means your Git history becomes a chain of working states. You can always go back to any of them.

---

## ✅ Pattern 6: "Progressive Enhancement" — Get Basic Working, Then Polish

### The Pattern

Build the simplest possible version of a feature first. Get it working. *Then* make it pretty, fast, and polished.

### Why It Works

Perfectionism is the enemy of progress. If you try to build the perfect feature in one shot, you'll either:
- Spend days and end up with something that doesn't work
- Get overwhelmed and quit
- Build something complicated that's hard to debug

Instead, build in layers:

### The Three Layers

1. **Layer 1 — Make it work** 🔨
   - The feature functions correctly
   - It might be ugly, slow, or clunky — that's fine
   - *"I can create a todo and it saves to the database"*

2. **Layer 2 — Make it right** ✅
   - Handle edge cases (what if the input is empty? what if the network fails?)
   - Add validation and error messages
   - *"It rejects empty todos and shows a helpful error"*

3. **Layer 3 — Make it nice** ✨
   - Polish the design
   - Add animations and transitions
   - Improve loading states and feedback
   - *"The todo slides in with a smooth animation and shows a success toast"*

### Example Progression

**Layer 1 prompt**: *"Create a contact form with name, email, and message fields. When submitted, save the data to Supabase."*

**Layer 2 prompt**: *"Now add validation: name is required, email must be valid, message must be at least 10 characters. Show inline error messages for each field."*

**Layer 3 prompt**: *"Polish the form: add smooth transitions for error messages, a loading spinner on the submit button, a success animation after submission, and make it fully responsive on mobile."*

---

## ❌ Anti-Pattern 1: "The Kitchen Sink" — Asking for Everything at Once

### The Trap

> *"Build me a complete SaaS app with user auth, Stripe payments, a dashboard with charts, an admin panel, email notifications, a REST API, role-based permissions, and a mobile-responsive design."*

### Why It Fails

This is like asking a contractor to build a house, a pool, a garage, and a guest house — all at the same time, in one day. The result will be a mess.

When you overload AI with too many requirements:
- It produces shallow, buggy code for everything
- Features conflict with each other
- It's impossible to debug because everything's tangled together
- You can't tell what works and what doesn't

### What to Do Instead

Break it into pieces. Build one feature at a time (see Pattern 2). Start with the core value of your app and expand from there.

---

## ❌ Anti-Pattern 2: "The Amnesia Loop" — Not Providing Context

### The Trap

Starting a new conversation with AI and saying:

> *"Add a delete button to the user card."*

...without telling the AI anything about your app, your tech stack, your file structure, or what a "user card" looks like in your project.

### Why It Fails

AI doesn't remember your project between conversations. Every new conversation starts with a blank slate. Without context, AI will:
- Guess your tech stack (and guess wrong)
- Create code that doesn't match your existing style
- Use different naming conventions
- Introduce incompatible patterns

### What to Do Instead

Start every new conversation with context:

> *"I'm building a client management tool using Next.js, Tailwind CSS, and Supabase. Here's my current project structure: [paste tree]. Here's my existing UserCard component: [paste code]. I want to add a delete button that removes the user from Supabase and updates the list."*

**Pro tip**: Keep a "context document" — a short summary of your project that you can paste at the start of every conversation. Include your tech stack, file structure, and key decisions. See our [Project Rules Starter Template](../../templates/project-rules-starter.md).

---

## ❌ Anti-Pattern 3: "The Perfectionist Trap" — Endless Refinement Before Shipping

### The Trap

Spending weeks polishing your app's design, tweaking animations, perfecting copy, and adding "just one more feature" — all before letting a single person use it.

### Why It Fails

You're optimizing in the dark. Without real users, you're guessing about what matters. And your guesses are usually wrong.

Common symptoms:
- *"I just need to fix this one more thing before I launch..."* (repeated for weeks)
- *"The color scheme isn't quite right yet..."*
- *"I should add feature X before anyone sees it..."*
- *"It's not ready for real users yet..."*

### What to Do Instead

Ship when your app does **one thing well**. Not perfectly — well enough.

Ask yourself: *"If someone used this app right now, would they get value from it?"* If yes, ship it.

Remember:
- Instagram launched with just photo filters — no videos, no stories, no reels
- Twitter launched as a simple SMS-based status updater
- Amazon started as an online bookstore

**Your version 1 should embarrass you a little.** If it doesn't, you waited too long to launch.

---

## ❌ Anti-Pattern 4: "Copy-Paste Blindness" — Accepting Code Without Understanding

### The Trap

AI gives you code. You paste it in. It works (or doesn't). You move on. You have no idea what the code actually does.

### Why It Fails

This works fine... until something breaks. And something *will* break. When it does, you'll be completely stuck because you don't understand what any of the code does.

More dangerous: you might paste in code that:
- Has security vulnerabilities
- Deletes data without confirmation
- Exposes API keys
- Sends user data to unknown servers

### What to Do Instead

You don't need to understand every line of code. But you should understand the **intent** of each block. After AI gives you code, ask:

> *"Can you explain what this code does in plain English? Walk me through it step by step like I'm a beginner."*

Look for:
- **What data does it handle?** (user info, payments, etc.)
- **What external services does it talk to?** (databases, APIs, third-party services)
- **What happens when something goes wrong?** (error handling)
- **Are there any security concerns?** (API keys in code, unvalidated input)

If something looks important or security-related, understand it before using it.

---

## ❌ Anti-Pattern 5: "The Tool Hopper" — Switching Tools Mid-Project

### The Trap

Starting your project with Cursor, then hearing about Lovable and switching. Then trying Bolt. Then going back to Claude. Then trying Windsurf. All on the same project.

### Why It Fails

Each tool has its own patterns, conventions, and quirks. Switching mid-project means:
- Your code becomes a Frankenstein mix of different styles
- You waste time re-explaining your project to each new tool
- You never get deep enough with any tool to use it effectively
- Context and history are lost with each switch

### What to Do Instead

**Pick one primary tool and stick with it for the entire project.** You can explore other tools on side projects, but don't hop mid-build.

If you're genuinely unhappy with your current tool:
1. Finish your current feature or reach a stable state
2. Commit everything to Git
3. *Then* try the new tool on a fresh branch or project
4. Only switch if the new tool is clearly better for your specific needs

---

## Quick Reference Card

### Patterns to Adopt ✅

| Pattern | One-Line Summary |
|---------|-----------------|
| UI First | Build what you see before what it does |
| One Feature Per Conversation | Keep AI focused on one thing at a time |
| Spec-Driven Development | Write what you want before asking AI to build it |
| Screenshot Prompting | Show AI what you want with pictures |
| The Undo Safety Net | Commit before every big change |
| Progressive Enhancement | Make it work → make it right → make it nice |

### Anti-Patterns to Avoid ❌

| Anti-Pattern | One-Line Summary |
|--------------|-----------------|
| The Kitchen Sink | Don't ask for everything at once |
| The Amnesia Loop | Always give AI context about your project |
| The Perfectionist Trap | Ship when it works, not when it's perfect |
| Copy-Paste Blindness | Understand what the code does before using it |
| The Tool Hopper | Pick one tool and stick with it |

---

## What's Next?

Now that you know the patterns that work, let's talk about something exciting: turning your vibe-coded app into a real business. Can you actually make money with this? (Spoiler: yes!)

---

> **Key Takeaway**: Successful vibe coding is about building smart habits. Start with UI, stay focused, write specs, commit often, and ship before it's perfect. Avoid the traps of overloading, losing context, and chasing perfection.

[← Previous: After Launch](../16-after-launch/README.md) | [Next: Building a Business →](../18-building-a-business/README.md)
