# Chapter 5: From Idea to PRD (Product Requirements Document)

> "If you don't know where you're going, any road will take you there." — Lewis Carroll (paraphrased)

You've got an idea for an app. Maybe it hit you in the shower, during a commute, or while you were frustrated with some tool that didn't do what you needed. That spark of "someone should build this" energy is exciting.

But here's the thing — jumping straight from idea to prompting is like trying to build a house without a blueprint. You might end up with walls in the wrong places and no room for a bathroom.

This chapter will teach you how to write a **simple, one-page PRD** — a Product Requirements Document — that turns your fuzzy idea into a clear plan. And yes, you can even use AI to help you write it.

---

## What's a PRD (and Why Should You Care)?

A PRD is just a fancy name for a **written plan for your app**. In big tech companies, product managers spend weeks writing these. But for solopreneurs doing vibe coding, you only need about one page.

### Why bother with a plan?

Think of it this way: if you were going on a road trip, would you just start driving and hope for the best? Probably not. You'd at least pick a destination, check the route, and make sure you had enough gas.

A PRD is your road trip plan for building an app:

1. **It saves you time.** Without a plan, you'll wander. You'll build features you don't need, redesign things three times, and end up frustrated. A PRD keeps you focused on what matters.

2. **It makes your prompts 10x better.** When you have a clear plan, every prompt you write to the AI will be more focused and specific. You'll build faster and get better results.

3. **It prevents "scope creep."** That's when your simple task manager slowly turns into a project management platform with Gantt charts, team features, and a built-in calendar. A PRD is your guardrail — it reminds you what you're actually building.

4. **It gives you a finish line.** One of the hardest parts of building something is knowing when it's "done." A PRD defines done for you.

---

## The 1-Page PRD Template for Vibe Coding

Here's the template. It's simple on purpose — you can fill it out in 15-20 minutes, and it'll save you hours of aimless building.

```markdown
# [App Name]

## One-Line Description
[What does this app do, in one sentence?]

## Target User
[Who is this for? Be specific — not "everyone."]

## Core Problem
[What pain point or frustration does this solve?]

## Must-Have Features (MVP)
1. [Feature 1]
2. [Feature 2]
3. [Feature 3]
4. [Feature 4]
5. [Feature 5]

## Nice-to-Have Features (v2 — build these LATER)
- [Feature A]
- [Feature B]
- [Feature C]

## Design Preferences
- Style: [minimal, playful, corporate, etc.]
- Colors: [any preferences, or "open to suggestions"]
- Reference sites: [apps or websites with a look you like]

## Technical Preferences (Optional)
- Framework: [if you have one in mind, e.g., Next.js, or "no preference"]
- Database: [e.g., Supabase, or "whatever works best"]
- Hosting: [e.g., Vercel, or "not sure yet"]
```

That's it. One page. Let's walk through each section so you know exactly what to write.

---

## Section-by-Section Guide

### App Name & One-Line Description

Your app name doesn't have to be clever or final — it's just a working title. And the one-line description forces you to distill your idea down to its essence.

**The test:** Could you explain this app to a friend in one sentence while waiting in line for coffee? If not, simplify.

- ✅ "A simple task manager that helps freelancers track projects and deadlines."
- ❌ "A comprehensive productivity and project management solution with integrated time tracking, invoicing, and client communication capabilities." (That's three apps pretending to be one.)

### Target User

This is the most important section that beginners skip. "Who is this for?" is not "everyone." The more specific you are, the better decisions you'll make.

Ask yourself:
- What do they do for a living?
- What's their biggest frustration?
- How tech-savvy are they?
- When and where would they use this app?

**Good:** "Freelance graphic designers who juggle 5-10 client projects and forget deadlines."

**Too broad:** "People who want to be productive." (That's literally everyone.)

### Core Problem

This answers: **why does this app need to exist?**

Don't describe your solution here — describe the pain. What's annoying, broken, or missing in your target user's life?

**Good:** "Freelancers lose track of project deadlines because they manage tasks across sticky notes, Slack messages, and email. They need one simple place to see everything."

**Weak:** "People need a task manager." (Why? There are hundreds of task managers already.)

### Must-Have Features (MVP)

MVP stands for **Minimum Viable Product** — the smallest version of your app that's actually useful to someone.

This is where discipline matters most. You want **3 to 5 features**, maximum. That's it. Not 10, not 15. Three to five.

How to choose: Ask yourself, "If the app ONLY had this feature, would it still solve the core problem?" If yes, it's a must-have. If not, it goes in the nice-to-have list.

**Tips for writing features:**
- Start each one with a verb (Add, Show, Let, Track, Send)
- Be specific about what the feature does
- Each feature should be small enough to build in one sitting

### Nice-to-Have Features (v2)

This is your parking lot for good ideas that you're not building yet. Writing them down here serves two purposes:

1. You won't forget them
2. You won't be tempted to build them now

Everything that's cool but not essential goes here. You'll come back to this list after your MVP is working.

### Design Preferences

You don't need to be a designer. Just answer:
- **What vibe do you want?** Clean and minimal? Fun and colorful? Professional and corporate?
- **Any colors?** Even "blue and white" is helpful.
- **What apps or sites look the way you want yours to look?** This is the most useful thing you can provide. "I want it to feel like Notion" tells the AI more than a paragraph of description.

### Technical Preferences

If you've already picked tools from Chapter 2, put them here. If you haven't, that's okay — just write "no preference" and let the AI suggest something when you start building.

---

## Worked Example: TaskFlow

Let's fill out the template for a real app idea, step by step.

```markdown
# TaskFlow

## One-Line Description
A simple task manager that helps freelancers track client projects
and never miss a deadline.

## Target User
Freelance designers, writers, and developers who manage 3-10 active
client projects at any given time. They're not super technical —
they want something simpler than Asana or Monday.com.

## Core Problem
Freelancers juggle multiple client projects with different deadlines.
They track tasks across sticky notes, email, and memory — and things
fall through the cracks. They need one simple place to see what's
due and what needs attention, without the complexity of enterprise
project management tools.

## Must-Have Features (MVP)
1. Add tasks with a title, description, and due date
2. Organize tasks by client/project (with color-coded labels)
3. Dashboard that shows tasks due today, this week, and overdue
4. Mark tasks as complete (with a satisfying checkmark animation)
5. Simple project view — click a project to see all its tasks

## Nice-to-Have Features (v2)
- Email reminders for upcoming deadlines
- Recurring tasks (e.g., "Send weekly client update")
- Time tracking per task
- Client portal where clients can see project progress
- Mobile app version (start with web only)

## Design Preferences
- Style: clean and minimal — not cluttered
- Colors: soft blue (#4361ee) as the primary color, white background,
  light gray for cards and borders
- Reference sites: Todoist (for simplicity), Linear (for the clean
  layout), Notion (for the overall feel)

## Technical Preferences
- Framework: Next.js (because it works well with Vercel for hosting)
- Database: Supabase (free tier, easy to set up)
- Hosting: Vercel (free tier for personal projects)
- Styling: Tailwind CSS
```

Notice a few things about this example:

- **The features are small and specific.** "Add tasks with a title, description, and due date" is something you can build in one prompting session. "Comprehensive project management" is not.
- **The nice-to-haves are genuinely nice-to-have.** The app works without email reminders or time tracking. Those are enhancements, not essentials.
- **The design section references real apps.** This gives the AI (and you) a shared visual vocabulary.

---

## The Meta Trick: Using AI to Write Your PRD 🤖

Here's something wonderfully meta: you can use AI to help you write the PRD itself. You bring the idea, the AI helps you organize it.

### The Prompt

```
I have an idea for an app and I need help turning it into a clear,
one-page Product Requirements Document (PRD).

Here's my idea: [describe your idea in a few sentences — be as
detailed or rough as you want]

The target user is: [who you imagine using this]

Please create a PRD with these sections:
1. App name (suggest one if I don't have one)
2. One-line description
3. Target user (expand on what I've provided)
4. Core problem it solves
5. 3-5 must-have features for an MVP (keep them small and buildable)
6. Nice-to-have features for v2
7. Design preferences (suggest a style that fits the target user)
8. Recommended tech stack for a beginner using vibe coding

Keep it practical and focused. I'm a solopreneur building this
with AI assistance, so everything should be scoped for one person
to build.
```

### Example: Using the Prompt

Let's say your idea is rough:

> "I want to build something that helps people track their daily habits. Like a simple thing where you check off what you did each day and can see your progress over time."

You'd plug that into the prompt above. The AI might come back with something like:

```markdown
# HabitStreak

## One-Line Description
A minimalist daily habit tracker that helps people build consistent
routines through visual progress tracking.

## Target User
Young professionals (25-35) who want to build better habits but
find apps like Habitica too gamified and complex. They want something
they can check in under 30 seconds each day.

## Core Problem
People struggle to build consistent habits because they lose track
of their progress and don't have a simple, visual way to see their
streaks. Existing habit apps are either too complex or too playful.

## Must-Have Features (MVP)
1. Add up to 10 daily habits with custom names and emoji icons
2. Daily check-in screen — tap to mark habits as done for today
3. Streak counter showing consecutive days for each habit
4. Weekly/monthly grid view (like GitHub's contribution graph)
5. Simple stats: current streak, longest streak, completion rate

## Nice-to-Have Features (v2)
- Push notification reminders
- Weekly email summary
- Social accountability (share streaks with a friend)
- Custom habit frequencies (e.g., 3x per week instead of daily)
- Data export

## Design Preferences
- Style: minimal, calming, modern
- Colors: soft greens and whites (green = growth/health)
- Reference: the simplicity of Apple's Health app, the grid view
  from GitHub contributions

## Recommended Tech Stack
- Next.js + Tailwind CSS for the frontend
- Supabase for database and authentication
- Vercel for hosting
```

### How to Refine the AI's Output

The AI's first draft is a starting point, not the final answer. Read through it and ask yourself:

- **Does the target user feel right?** If not, tell the AI to adjust.
- **Are the MVP features truly minimal?** If there are more than 5, ask the AI to cut the least essential ones.
- **Do the design suggestions match your vision?** If you hate green, say so.
- **Is anything missing?** Add your own ideas.

You can follow up with prompts like:

> "This is great, but I want to change the target user to busy parents, not young professionals. Also, can we cut it down to 4 must-have features? I want to start as small as possible."

Iterate until the PRD feels like YOUR app, not a generic template.

---

## From PRD to First Prompt

Now comes the magic moment — turning your PRD into your very first vibe coding prompt.

Here's the approach:

### Step 1: Start with project setup

Your first prompt should set up the foundation. Pull from your PRD:

```
I'm building [app name]: [one-line description].

Tech stack: [from your PRD].

Set up a new project with:
- The basic project structure
- A homepage with a [describe what the landing page should show]
- Navigation with links for: [list your main pages based on MVP features]
- [Your design preferences from the PRD]

Don't add any features yet — just the skeleton of the app.
```

### Step 2: Add features one at a time

Then go through your must-have features list, one prompt per feature:

```
Now add the first feature from my PRD: [Feature 1 description].

Here's what it should do:
- [Detail from your PRD]
- [More detail]

[Design constraints from your PRD]
```

### Step 3: Reference your PRD as context

As you build, you can paste your PRD (or parts of it) at the start of conversations to give the AI context:

```
Here's the PRD for my project:
[paste relevant sections]

Now I'd like to work on [specific feature].
```

This keeps the AI aligned with your overall vision, even as you work on tiny pieces.

---

## Common Mistakes to Avoid

### 1. Feature Creep ("Oh, It Should Also...")

This is the #1 project killer for solopreneurs. You start with a simple idea, and then:

- "Oh, it should also have user profiles..."
- "And a notification system..."
- "And maybe an admin dashboard..."
- "And API integrations with..."

Before you know it, your simple app has 30 features and you've been building for months without launching anything.

**The fix:** If a new idea comes up while building, add it to the "Nice-to-Have" section of your PRD and keep going. Don't build it now. Ship your MVP first, then decide if you even need it.

### 2. No Clear User

If you can't describe your target user in one specific sentence, your app will try to be everything for everyone — and end up being nothing for nobody.

**The fix:** Pick ONE type of person. Build for them. You can always expand later, but start narrow.

### 3. Trying to Build Everything at Once

If your MVP has more than 5 features, it's not an MVP — it's a full product. And full products take months, not weeks.

**The fix:** Be ruthless. Ask yourself: "Could someone find this useful with ONLY these features?" If yes, that's your MVP. Everything else waits.

### 4. Skipping the PRD Entirely

"I'll just figure it out as I go" feels faster, but it's not. You'll change direction, rebuild things, and lose motivation when the project feels endless.

**The fix:** Spend 20 minutes on a PRD. That's it. Twenty minutes of planning will save you twenty hours of wandering.

---

## Your Turn: Write Your PRD 📝

It's time to try this yourself. Grab a notes app (or use the AI) and fill out the template for YOUR app idea.

If you don't have an app idea yet, no worries — here are a few starter ideas to practice with:

- **BookShelf:** A personal library tracker for people who read a lot
- **MealPlan:** A weekly meal planner that generates grocery lists
- **InvoiceSnap:** A simple invoicing tool for freelancers
- **FitLog:** A workout tracker that doesn't require a gym membership
- **PetCare:** A pet care reminder app for medication, vet visits, and feeding schedules

Pick one (or use your own idea) and fill out every section of the template. Then try the meta trick — use AI to help you refine it.

---

## Key Takeaways

1. **A PRD is your blueprint.** Even a simple one-page plan saves you hours of aimless building.
2. **Be specific about your target user.** "Everyone" is not a user.
3. **Keep your MVP to 3-5 features.** If it's more, you're building too much.
4. **Use AI to write your PRD.** It's great at turning rough ideas into structured plans.
5. **Your PRD powers your prompts.** Every prompt you write will be better because you know exactly what you're building.

---

## What's Next?

You've got your PRD. You know how to write great prompts. But what happens when you start a new conversation with the AI and it forgets everything about your project? In the next chapter, we'll tackle **context engineering** — how to keep the AI up to speed on your project, every single time.

[→ Chapter 6: Context Engineering for Beginners](../06-context-engineering/README.md)
