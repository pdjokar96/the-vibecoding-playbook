# 🧰 Prompt Templates for Vibe Coding

Copy-paste these prompts directly into your AI assistant. Customize the bracketed `[sections]` with your specific details. These are battle-tested prompts that get great results.

---

## 🧠 Ideation Prompts

### 1. Validate a Business Idea

```
I have an idea for an app: [describe your idea in 2-3 sentences].

My target audience is [describe who would use it].

Please help me think through:
1. Does this solve a real problem? What's the pain point?
2. What existing solutions do people use today?
3. Why would someone switch to my app?
4. What's the simplest version (MVP) I could build to test this?
5. How could I make money from this?

Be honest — if there are red flags, tell me.
```

### 2. Generate App Ideas for a Niche

```
I'm a [your profession/role] and I work with [your clients/audience].

The biggest pain points I see daily are:
1. [Pain point 1]
2. [Pain point 2]
3. [Pain point 3]

Suggest 5 app ideas I could build to solve these problems. For each idea, include:
- A one-line description
- Who would pay for it
- How I could charge for it
- How complex it would be to build (simple/medium/complex)
```

### 3. Write a One-Page PRD

```
Help me write a Product Requirements Document for this app idea:

[Describe your app idea in a paragraph]

Include these sections:
1. Problem Statement
2. Target User (be specific)
3. Core Features (MVP only — max 5)
4. User Flows (main paths through the app)
5. Success Metrics
6. What's NOT in scope

Keep it concise — aim for about 1 page.
```

---

## 🏗️ Building Prompts

### 4. Start a New Project

```
I want to build [describe your app]. Here's what I need:

**Target users**: [who is this for]
**Core features**:
1. [Feature 1]
2. [Feature 2]
3. [Feature 3]

**Design style**: [e.g., clean and minimal, like Notion]
**Auth needed**: [Yes/No — if yes, what type: email/password, Google login, etc.]
**Database needed**: [Yes/No — if yes, what data needs to be stored]

Please set up the project structure and build the first screen. Use [Next.js/React/etc. or "whatever you recommend"] with [Tailwind CSS/etc. or "whatever looks good"].
```

### 5. Add a New Feature

```
I'm building [app name], a [brief description].

**Tech stack**: [e.g., Next.js, Tailwind, Supabase]
**Current state**: [describe what's already built]

I want to add: [describe the feature]

Here's how it should work:
1. [Step 1 of the user flow]
2. [Step 2]
3. [Step 3]

Please implement this feature. Handle error cases gracefully (show user-friendly messages, don't just fail silently).
```

### 6. Build a Complete Page/Screen

```
Create a [page name] page for my [app type] app.

**Layout**:
- [Describe the header/nav]
- [Describe the main content area]
- [Describe the sidebar if any]
- [Describe the footer if any]

**Components on this page**:
1. [Component 1 — e.g., "A search bar at the top"]
2. [Component 2 — e.g., "A grid of cards showing projects"]
3. [Component 3 — e.g., "A floating action button to add new items"]

**Data**: [Where does the data come from? Database? API? Hardcoded for now?]
**Design**: [Reference an existing page for consistency, or describe the style]

Make it fully responsive — should work on both desktop and mobile.
```

### 7. Connect to a Database

```
I need to set up a database for my app. Here's what I need to store:

**Users**: [list fields — e.g., name, email, avatar, plan type]
**[Entity 2]**: [list fields — e.g., Projects: title, description, status, due date, owner]
**[Entity 3]**: [list fields — e.g., Tasks: title, completed, project it belongs to]

**Relationships**:
- [e.g., Each user can have many projects]
- [e.g., Each project can have many tasks]
- [e.g., Each task belongs to one project]

I'm using [Supabase/Firebase/other]. Please:
1. Create the database tables/schema
2. Set up Row Level Security (users can only see their own data)
3. Create helper functions for CRUD operations (create, read, update, delete)
4. Show me how to use them in my app
```

---

## 🐛 Debugging Prompts

### 8. Fix an Error

```
I'm getting this error in my [app type] app:

```
[Paste the exact error message here]
```

**When does it happen**: [e.g., "When I click the submit button on the form"]
**What should happen**: [e.g., "The form data should save to the database"]
**What actually happens**: [e.g., "Nothing happens, and this error shows in the console"]

**Relevant code**:
```
[Paste the relevant code file or section]
```

Please explain what's wrong in plain English and provide the fix.
```

### 9. Something Doesn't Look Right

```
My [component/page] doesn't look the way I want.

**What I expected**: [Describe or attach a screenshot of what you want]
**What I'm seeing**: [Describe or attach a screenshot of what's actually happening]

**Current code**:
```
[Paste the component code]
```

Please fix the styling so it matches what I described. Keep it responsive.
```

### 10. My App Is Slow

```
My app feels slow. Here's what's happening:

**What's slow**: [e.g., "The dashboard takes 5+ seconds to load"]
**How much data**: [e.g., "About 200 records in the database"]
**Current approach**: [e.g., "I'm fetching all records on page load"]

Please help me:
1. Identify why it's slow
2. Suggest the simplest fix
3. Implement the fix

I'd rather have a simple solution that improves things 80% than a complex one that's perfect.
```

---

## 🎨 Design Prompts

### 11. Improve the Look and Feel

```
My app works but it looks basic. Here's my current [page/component]:

```
[Paste current code]
```

Please redesign it to look more professional and polished. Specifically:
1. Better spacing and layout
2. Consistent typography
3. Subtle shadows or borders to create depth
4. A cohesive color scheme using [your preferred colors or "whatever looks good"]
5. Smooth hover effects on interactive elements
6. A loading state for any async operations

Keep the same functionality — just make it look great. Use [Tailwind CSS/your styling approach].
```

### 12. Make It Mobile-Friendly

```
My [page/component] looks good on desktop but breaks on mobile.

Here's the current code:
```
[Paste code]
```

Please make it fully responsive:
- Mobile (< 640px): [describe desired mobile layout — e.g., "stack everything vertically"]
- Tablet (640-1024px): [describe desired tablet layout — e.g., "2 columns instead of 3"]
- Desktop (> 1024px): [keep current layout or describe changes]

Test that touch targets are large enough (at least 44x44px) and text is readable without zooming.
```

---

## 🔒 Security Review Prompts

### 13. Security Audit

```
Please review my app's security. Here are the key files:

**Authentication**: [paste auth-related code]
**API routes/endpoints**: [paste API code]
**Database queries**: [paste database code]
**Environment variables used**: [list them, NOT their values]

Check for:
1. Are API keys or secrets exposed in client-side code?
2. Can users access data that doesn't belong to them?
3. Are inputs properly validated and sanitized?
4. Are there any SQL injection or XSS vulnerabilities?
5. Is authentication properly checked on all protected routes?
6. Are sensitive operations (delete, update) properly authorized?

For each issue found, explain the risk in plain English and provide a fix.
```

---

## 🧪 Testing Prompts

### 14. Manual Test Plan

```
I just built [feature name] for my [app type] app.

Here's what it does: [describe the feature]

Please create a manual testing checklist I can walk through to make sure everything works. Include:
1. Happy path tests (everything works correctly)
2. Edge cases (empty inputs, very long text, special characters)
3. Error cases (network down, invalid data, unauthorized access)
4. Mobile testing (does it work on a phone?)
5. Browser testing (any known cross-browser issues?)

Format it as a checklist I can check off.
```

---

## 🚀 Deployment Prompts

### 15. Deploy My App

```
I'm ready to deploy my app. Here's my setup:

**Tech stack**: [e.g., Next.js, Tailwind, Supabase]
**Where I want to deploy**: [e.g., Vercel, Railway, or "wherever's easiest and free"]
**Database**: [e.g., Already on Supabase, or "need to set one up"]
**Environment variables I use**: [list variable NAMES only, not values]
**Custom domain**: [Yes/No — if yes, what domain]

Please give me step-by-step deployment instructions including:
1. Any changes needed in my code before deploying
2. Build configuration
3. Environment variable setup on the hosting platform
4. Database connection in production
5. How to verify the deployment works
6. How to set up auto-deploy from GitHub
```

### 16. Fix a Deploy Failure

```
My deployment to [Vercel/Railway/etc.] failed. Here are the build logs:

```
[Paste the build logs or error messages]
```

My app works fine locally. Please:
1. Explain what went wrong in plain English
2. Tell me exactly how to fix it
3. Suggest how to prevent this in the future
```

---

## 💡 Tips for Better Prompts

1. **Be specific**: "Add a blue button" is worse than "Add a blue (#2563EB) button with white text, rounded corners, and a hover effect that darkens the color slightly"

2. **Provide context**: Always tell the AI your tech stack, what's already built, and what you're trying to achieve

3. **Show, don't just tell**: Paste your current code, share screenshots, link to design inspiration

4. **One thing at a time**: Don't ask for 5 features in one prompt. Build one, verify it works, then move to the next

5. **Ask for explanations**: Add *"explain what the code does in plain English"* to any prompt to learn as you go

6. **Include constraints**: Tell the AI what you DON'T want — *"Don't use any external libraries for this"* or *"Keep it simple, no fancy animations"*

7. **Iterate**: If the first result isn't right, refine your prompt rather than starting over — *"That's close, but I want the sidebar to be fixed position and the cards to be in a 3-column grid"*
