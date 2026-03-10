# 🎨 Prompts for UI/UX Design

> Great design isn't about being an artist — it's about making things easy and pleasant to use. These prompts will help you create beautiful, user-friendly interfaces with AI, even if you've never opened a design tool. Swap out the `[placeholders]` with your own details!

---

## Designing Layouts

### 1. Generate a page layout

```
I'm building a [type of app, e.g., "simple invoicing app for freelancers"].
Design the layout for the [page name, e.g., "dashboard"] page. Describe:

- What goes in the header/navigation
- The main content area (what the user sees first)
- The sidebar (if any)
- The footer
- Where the primary call-to-action button goes

Describe it like you're explaining it to someone who can't see a screen — be
super specific about what goes where. Then write the HTML and CSS (using
Tailwind CSS) to build it.
```

### 2. Design a landing page

```
I need a landing page for my app called [App Name]. It [describe what it does
in one sentence]. My target users are [describe audience].

Design a landing page with these sections:
- Hero section with headline, subheadline, and a call-to-action button
- 3 feature highlights with icons
- A "How it works" section (3 simple steps)
- Social proof / testimonial section (I'll fill in later)
- A final call-to-action section
- Footer with links

Use a clean, modern style. Write the code using [React/HTML/your framework]
with Tailwind CSS.
```

### 3. Create a mobile-first layout

```
I have a [type of app] and I want the [page name] page to look great on
phones first, then scale up nicely to tablets and desktops.

Design a mobile-first layout. Start with the phone version — what stacks
vertically? Then describe how it rearranges on bigger screens. Write the
responsive code using Tailwind CSS breakpoints (sm, md, lg).
```

---

## Choosing Colors

### 4. Generate a color palette

```
I'm building an app for [describe your audience and what the app does].
The mood I want is [pick some: trustworthy / fun / calm / energetic / premium /
friendly / bold / minimalist].

Suggest a color palette with:
- Primary color (main brand color)
- Secondary color (accent)
- Background color
- Text color
- Success, warning, and error colors

Give me the exact hex codes and show me how to set them up as CSS variables
or Tailwind config. Also explain WHY you chose each color.
```

### 5. Fix my ugly color scheme

```
My app currently uses these colors: [list your current colors or paste your
CSS/Tailwind config]. It looks [describe the problem: "muddy," "too loud,"
"boring," "like a children's toy," etc.].

Suggest a better color palette that keeps roughly the same vibe but looks
more polished and professional. Show me a before/after comparison of how
a button, card, and navbar would look with the old vs. new colors.
```

---

## Responsive Design

### 6. Make my page responsive

```
Here's the code for my [page name] page:

[paste your code]

This looks fine on desktop but breaks on mobile. Can you:
1. Identify what's breaking on smaller screens
2. Fix the responsive issues
3. Make sure it works on phones (320px+), tablets (768px+), and desktops (1024px+)
4. Use Tailwind responsive classes (sm:, md:, lg:)

Explain each change you make so I can learn from it.
```

### 7. Design a responsive navigation

```
I need a navigation bar for my app that:
- Shows the logo and links horizontally on desktop
- Collapses into a hamburger menu on mobile
- Has smooth open/close animation on mobile
- Highlights the current page

Build this using [React/HTML] and Tailwind CSS. Include the JavaScript
needed for the mobile menu toggle. Keep it simple — I'm a beginner.
```

---

## Improving UX

### 8. Review my app's user experience

```
I'm building a [describe your app]. Here's how a user currently completes
[key task, e.g., "creating a new invoice"]:

1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Step 4]
5. [Step 5]

This feels clunky. Can you:
- Identify which steps could be removed or combined
- Suggest where I should add helpful defaults or auto-fill
- Recommend where to add confirmation messages or progress indicators
- Redesign the flow to be as simple as possible

Remember: my users are [describe them] and they're not tech-savvy.
```

### 9. Add empty states and loading states

```
My app has a [describe page/component, e.g., "project list page"]. Right now
when there's no data, it just shows a blank white screen. And when data is
loading, nothing happens — the user just stares at a frozen screen.

Design and code:
1. An empty state (when the user has no [items] yet) — include a friendly
   message, a nice illustration/icon, and a call-to-action button
2. A loading state with a skeleton screen or spinner
3. An error state for when something goes wrong

Use [React/your framework] and Tailwind CSS. Make it feel friendly, not scary.
```

### 10. Write helpful error messages

```
My app shows these error messages to users:

- "Error 422: Unprocessable entity"
- "null is not an object"
- "Network request failed"

Rewrite each one in plain, friendly language that:
- Tells the user what went wrong (in words they understand)
- Tells them what to do next
- Doesn't make them feel stupid

Also give me a general template I can follow for writing good error messages
throughout my app.
```

---

## Making Accessible UIs

### 11. Audit my page for accessibility

```
Here's the code for my [page/component]:

[paste your code]

Review it for accessibility issues. Check for:
- Missing alt text on images
- Poor color contrast
- Missing labels on form fields
- Keyboard navigation problems
- Missing ARIA attributes
- Heading hierarchy issues

For each issue, explain what's wrong in simple terms and show me the fixed code.
I want my app to be usable by everyone, including people using screen readers.
```

### 12. Design an accessible form

```
I need a [type of form, e.g., "sign-up form"] with these fields:
- [Field 1]
- [Field 2]
- [Field 3]

Build it with proper accessibility baked in from the start:
- Labels connected to inputs
- Helpful placeholder text
- Clear error messages that screen readers can announce
- Logical tab order
- Visible focus styles

Use [React/HTML] and Tailwind CSS. Add comments explaining why each
accessibility feature matters.
```

---

## Creating Design Systems

### 13. Build a simple component library

```
I'm building a [type of app] and I want consistent-looking UI throughout.
Create a mini design system with these reusable components:

1. Button (primary, secondary, danger, disabled states)
2. Input field (with label, placeholder, error state)
3. Card (with image, title, description, action)
4. Badge/tag (different colors for different statuses)
5. Alert/notification (success, warning, error, info)

Use [React/your framework] and Tailwind CSS. Make each component accept
props so I can customize them. Show me an example of using each one.
```

### 14. Establish typography and spacing rules

```
I want my app to look clean and professional. Set up a typography and
spacing system for me:

- Font choices (suggest a free Google Font pairing: one for headings, one for body)
- Font sizes for h1, h2, h3, body text, small text, and captions
- Line heights and letter spacing
- A consistent spacing scale (margins and padding)

Write this as Tailwind config (or CSS variables) and show me a sample page
that uses the system. Explain the reasoning so I can make good choices later.
```

---

## 💡 Tips for Better Design Prompts

- **Show, don't just tell.** Paste your actual code into the prompt for specific feedback.
- **Name your audience.** "Make it look good" is vague. "Make it trustworthy for small business owners in their 40s" gives the AI something to work with.
- **Reference examples.** Say "I like how Stripe's dashboard looks" or "I want the vibe of Linear's landing page."
- **Ask for explanations.** Add "Explain your design choices" so you learn, not just copy.
- **Iterate.** "I like this but the buttons feel too small and the header is too busy — simplify it."

---

*Part of [The Vibe Coding Playbook](../README.md) — a guide for building real apps with zero coding experience.*
