# Chapter 4: Talking to AI — Prompting 101

> "The quality of your app depends on the quality of your prompts."

You've picked your tools. You've built your first tiny app. Now it's time to learn the single most important skill in vibe coding: **talking to AI effectively**.

Think of it this way — an AI coding assistant is the most talented developer you'll ever work with, but it can only read your messages. It can't read your mind. The better you communicate what you want, the better the result you'll get back.

This chapter will teach you how to write prompts that get you exactly what you need, the first time (or at least close to it).

---

## Why Prompting Matters

Here's a truth that surprises most beginners: **the hard part of vibe coding isn't the code — it's describing what you want clearly.**

When you write a vague prompt, you get vague results. When you write a specific, well-structured prompt, you get code that actually does what you had in mind.

It's the difference between:
- ❌ Getting something you have to throw away and start over
- ✅ Getting something that's 90% right and just needs a small tweak

Good prompting saves you hours of back-and-forth. It's not about learning fancy techniques — it's about being clear, specific, and organized in how you ask for things.

---

## The Waiter Analogy 🍽️

Imagine you walk into a restaurant and say to the waiter:

> "Bring me food."

What happens? The waiter has no idea what you want. They might bring you a salad when you wanted a steak. They might bring you something you're allergic to. They'll probably just stare at you and ask a bunch of follow-up questions.

Now imagine you say:

> "I'd like a medium-rare ribeye steak with mashed potatoes and steamed broccoli on the side. No butter on the broccoli, please."

That's a completely different experience. The waiter knows exactly what to do, and you're going to get what you want.

**Prompting works the same way.** The AI is your waiter. If you say "make me an app," it has to guess what you want. But if you describe the dish — er, feature — in detail, you'll get something delicious.

---

## The Anatomy of a Good Prompt

Every great prompt has four parts. You don't always need all four, but the more you include, the better your results will be.

### The C-T-C-E Framework

| Part | What It Does | Example |
|------|-------------|---------|
| **Context** | Tells the AI about your project and situation | "I'm building a task manager app using React and Supabase." |
| **Task** | What you actually want it to do | "Add a feature that lets users set due dates on tasks." |
| **Constraints** | Rules, limits, or preferences | "Use a simple date picker, no external libraries. Keep it mobile-friendly." |
| **Examples** | What the result should look like | "Similar to how Todoist shows due dates as small text under each task." |

Let's see how this plays out with a real example.

**Bad prompt:**
> "Add due dates."

**Good prompt:**
> "I'm building a task manager app with React and Supabase (Context). Add a feature that lets users set a due date when creating or editing a task (Task). Use a native HTML date input — don't add any new libraries. The due date should be optional, and tasks past their due date should show in red (Constraints). Similar to how Todoist displays due dates as small, gray text beneath each task title (Example)."

See the difference? The second prompt gives the AI everything it needs to build exactly what you're imagining.

---

## 5 Prompt Templates You'll Use All the Time

Here are five go-to prompts that cover most of what you'll do in vibe coding. Feel free to copy and adapt them.

---

### Template 1: "Build Me a Feature"

Use this when you want to add something new to your app.

```
I'm building [brief project description] using [tech stack].

Add a [feature name] that:
- [What it does — behavior 1]
- [What it does — behavior 2]
- [What it does — behavior 3]

Requirements:
- [Any constraints: mobile-friendly, no new libraries, etc.]
- [Where it should appear in the app]
- [How it connects to existing features]

For reference, I want it to feel similar to [example app or website].
```

**Example in action:**

```
I'm building a habit tracker app using Next.js and Tailwind CSS.

Add a "streak counter" feature that:
- Shows how many days in a row the user has completed a habit
- Displays a small flame emoji 🔥 next to habits with a streak of 3+ days
- Resets the streak to zero if the user misses a day

Requirements:
- The streak should be calculated from the existing habit completion data
- Display the streak count on the main habits list page
- Keep the design minimal — just a small number next to each habit

For reference, I want it to feel similar to how Duolingo shows streak counts.
```

---

### Template 2: "Fix This Bug"

Use this when something isn't working right.

```
I'm working on [project description].

There's a bug: [describe what's happening].

What I expected: [what SHOULD happen].
What actually happens: [what's going wrong].

Steps to reproduce:
1. [Step 1]
2. [Step 2]
3. [Step 3]

Here's the relevant code:
[paste the code or file where you think the issue might be]

Error message (if any):
[paste the error message]
```

**Example in action:**

```
I'm working on a recipe-sharing app built with React.

There's a bug: when I click "Save Recipe," the page refreshes but the
recipe doesn't actually save to the database.

What I expected: the recipe should save and appear in my "My Recipes" list.
What actually happens: the page refreshes, no error shows up, but the
recipe isn't in the database.

Steps to reproduce:
1. Go to "Add New Recipe"
2. Fill in a title and at least one ingredient
3. Click "Save Recipe"
4. Check "My Recipes" — the new recipe isn't there

Here's the save function in RecipeForm.jsx:
[paste code here]

No error message appears in the browser, but the console shows:
"POST /api/recipes 401 Unauthorized"
```

**Pro tip:** The more specific you are about what's going wrong, the faster the AI can find the fix. "It doesn't work" tells the AI almost nothing. "It saves but doesn't show up in the list" tells it exactly where to look.

---

### Template 3: "Make It Look Like X"

Use this when you have a visual design in mind.

```
I want to update the [page/component] in my [project description].

Current state: [describe what it looks like now, or say "unstyled"].

I want it to look like: [describe the visual style].

Specific details:
- Colors: [list colors or say "match the screenshot"]
- Layout: [how things should be arranged]
- Typography: [font sizes, weights — or just "clean and modern"]
- Spacing: [compact, spacious, etc.]

Reference: [describe a website/app that has the look you want, or say
"I've attached a screenshot" if your tool supports image input].
```

**Example in action:**

```
I want to update the login page in my freelancer dashboard app.

Current state: it's just a plain, unstyled form with email and password fields.

I want it to look like a modern SaaS login page:

Specific details:
- Colors: white background, dark navy (#1a1a2e) for the header text,
  blue (#4361ee) for the login button
- Layout: centered card on the page, logo at the top, form fields stacked
  vertically, "Forgot password?" link below the button
- Typography: clean sans-serif font, large bold heading that says "Welcome back"
- Spacing: generous padding inside the card, comfortable spacing between fields

Reference: similar to the Notion login page — minimal, clean, centered.
```

**Pro tip:** If your AI tool supports images (like Cursor, Claude, or ChatGPT), you can paste a screenshot and say "Make it look like this." That's often the fastest approach for design work.

---

### Template 4: "Refactor / Improve This"

Use this when your code works but feels messy or could be better.

```
Here's a [file/function/component] from my [project description]:

[paste the code]

Please improve this code:
- [What specifically to improve: readability, performance, organization]
- [Any patterns to follow]
- [What NOT to change: "Don't change the overall behavior"]

Keep the same functionality — just make the code cleaner and easier
to maintain.
```

**Example in action:**

```
Here's the main App.jsx file from my budget tracker app:

[paste code — imagine it's a 200-line file with everything crammed in]

Please improve this code:
- Split it into smaller components (each feature should be its own component)
- Move the API calls into a separate utility file
- Add clear comments explaining what each section does
- Don't change the overall behavior — everything should work the same way

Keep the same functionality — just make the code cleaner and easier
to maintain.
```

---

### Template 5: "Explain What This Does"

Use this when you encounter code you don't understand.

```
I'm new to coding and I'm working on [project description].

Can you explain what this code does in plain English?

[paste the code]

Specifically:
- What is the overall purpose of this code?
- Walk me through it step by step
- Are there any important things happening that I should be aware of?
- [Any specific part you're confused about]

Please explain it like I've never coded before — use analogies
if they help.
```

**Example in action:**

```
I'm new to coding and I'm working on a weather app.

Can you explain what this code does in plain English?

useEffect(() => {
  const fetchWeather = async () => {
    const response = await fetch(
      `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${API_KEY}`
    );
    const data = await response.json();
    setWeather(data);
  };
  fetchWeather();
}, [city]);

Specifically:
- What does useEffect do here?
- What does "async" and "await" mean?
- Why is [city] in brackets at the end?

Please explain it like I've never coded before.
```

Understanding what your code does — even at a basic level — makes you a much more effective vibe coder. You don't need to memorize syntax, but knowing the "why" behind things helps you make better decisions.

---

## 🔴 Anti-Patterns: What NOT to Do

Let's look at the most common prompting mistakes and why they fail.

---

### Anti-Pattern 1: Too Vague

**The prompt:**
> "Make it better."

**Why this fails:** Better how? Faster? Prettier? More features? The AI has no idea which direction to go, so it'll guess — and it'll probably guess wrong.

**The fix:**
> "The dashboard page loads slowly. Optimize the data fetching so it loads in under 2 seconds. Focus on reducing the number of API calls."

See? Now the AI knows exactly what "better" means to you.

---

### Anti-Pattern 2: Too Much at Once

**The prompt:**
> "Build me an e-commerce site with user accounts, a product catalog, shopping cart, payment processing, order tracking, an admin panel, email notifications, and a recommendation engine."

**Why this fails:** This is like asking a builder to construct an entire house in one afternoon. Even if the AI tries, the result will be a tangled mess of half-working features. You'll spend more time fixing it than you saved.

**The fix:** Break it into small, focused steps:
1. "Set up the project with a basic homepage and navigation"
2. "Add a product catalog page that displays products from a database"
3. "Add a shopping cart that lets users add/remove products"
4. And so on...

Each prompt builds on the last one. Small steps = solid foundation.

---

### Anti-Pattern 3: No Context

**The prompt:**
> "Add a login page."

**Why this fails:** The AI doesn't know anything about your project. What tech are you using? Do you already have a database? Is this a mobile app or a website? Without context, the AI will make assumptions that probably don't match your setup.

**The fix:**
> "I'm building a Next.js app with Supabase for the backend. I already have a database with a `users` table. Add a login page using Supabase Auth with email and password. After successful login, redirect the user to `/dashboard`."

Context is everything. Always tell the AI what it's working with.

---

### Anti-Pattern 4: Not Providing Error Messages

**The prompt:**
> "It's broken. Fix it."

**Why this fails:** The AI can't see your screen. It doesn't know what "broken" means to you. Is there an error? Does the page look wrong? Does a button not work?

**The fix:**
> "When I click the Submit button, I get this error in the browser console: `TypeError: Cannot read properties of undefined (reading 'map')`. Here's the component code: [paste code]. The form was working before I added the filter feature."

Always include error messages — they're like clues that help the AI solve the mystery.

---

## The Golden Rule: One Change Per Prompt ✨

If there's one rule to follow, it's this:

> **Ask for one thing at a time.**

When you're building your app, resist the temptation to ask for three features in one prompt. Here's why:

1. **Easier to test.** When you make one change, you can immediately check if it works. If something breaks, you know exactly what caused it.

2. **Easier to undo.** If the AI's response isn't what you wanted, you can throw it away and try again — without losing other work.

3. **Better results.** AI gives more accurate, focused output when it's working on one clear task.

Think of it like stacking blocks. You place one block, make sure it's stable, then place the next. If you try to stack five blocks at once, they all fall down.

### The Rhythm of Vibe Coding

It goes like this:

```
1. Write a clear, focused prompt (one thing)
2. Review what the AI gives you
3. Test it — does it work?
4. If yes → commit/save and move to the next prompt
5. If no → tell the AI what's wrong and ask it to fix it
6. Repeat
```

This cycle is your new best friend. Get comfortable with it, and you'll build apps faster than you ever thought possible.

---

## Practice Exercise: Rewrite a Bad Prompt 📝

Let's put your new skills to the test. Here's a bad prompt. Your job is to rewrite it as a good one.

### The Bad Prompt

> "I need a page where users can see stuff and do things with it. Make it look nice. Also add a way to search."

Take a minute. What's wrong with this prompt?

Let's break it down:
- **"See stuff"** — What stuff? Products? Blog posts? Photos?
- **"Do things with it"** — What things? Edit? Delete? Share? Buy?
- **"Make it look nice"** — What does "nice" mean? Modern? Colorful? Minimal?
- **"Add a way to search"** — Search by what? Name? Category? Date?

### A Rewritten Version

Here's one way to rewrite it using the C-T-C-E framework:

```
I'm building a recipe-sharing app with React and Supabase.

Create a "Browse Recipes" page that:
- Displays all recipes as cards in a responsive grid (3 columns on
  desktop, 1 on mobile)
- Each card shows: recipe photo, title, cook time, and number of
  servings
- Clicking a card opens the full recipe detail page

Add a search bar at the top of the page:
- Users can search recipes by title or ingredient
- Search results update as the user types (filter the visible cards,
  don't make a new API call each time)
- Show a "No recipes found" message if the search has no results

Design style:
- Clean and minimal, white background
- Rounded corners on the cards with a subtle shadow
- Similar to the recipe grid on Allrecipes.com

Use the existing `recipes` table in Supabase, which has columns:
id, title, image_url, cook_time, servings, ingredients, instructions.
```

That's a prompt the AI can actually work with.

---

## Quick Reference Card

When you're writing your next prompt, run through this checklist:

- [ ] **Context:** Did I explain my project and tech stack?
- [ ] **Task:** Did I clearly state what I want?
- [ ] **Constraints:** Did I mention any rules or limitations?
- [ ] **Examples:** Did I reference something similar?
- [ ] **One thing:** Am I asking for just one feature/change?
- [ ] **Specific:** Would a stranger understand exactly what I mean?

If you can check most of these boxes, you're writing great prompts.

---

## Key Takeaways

1. **Be specific.** Vague prompts get vague results. Describe exactly what you want like you're ordering from a menu.
2. **Use the C-T-C-E framework.** Context, Task, Constraints, Examples. You don't need all four every time, but the more you include, the better.
3. **One change per prompt.** Build your app step by step, not all at once.
4. **Include error messages.** When something breaks, always share the error.
5. **Practice makes better.** Your first prompts might be rough — that's okay. You'll get faster and more natural with every project.

---

## What's Next?

Great prompts start with a clear vision. In the next chapter, we'll take your app idea and turn it into a simple product requirements document (PRD) — a one-page blueprint that makes your prompts even better.

[→ Chapter 5: From Idea to PRD](../05-idea-to-prd/README.md)
