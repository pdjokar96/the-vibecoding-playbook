# Chapter 3: Your First App in 30 Minutes ⏱️

[← Previous: Choosing Your Tools](../02-choosing-your-tools/) · [Back to Playbook](../../README.md) · [Next: Prompting 101 →](../04-prompting-101/)

---

## Let's Build Something Real

Enough reading. It's time to build.

In this chapter, you're going to create a **personal portfolio website** — a real, working app that you can share with anyone via a link. It will have:

- A **hero section** with your name and a short bio
- An **about me** section
- A **project gallery** to showcase your work
- A **contact form** so people can reach you

We've prepared two paths. Pick the one that fits you:

| Path | Tool | Setup Time | Best For |
|------|------|-----------|----------|
| **Path A** | Lovable | 0 minutes (browser only) | Complete beginners — no installs, no terminal, no friction |
| **Path B** | Cursor | 10 minutes (desktop app) | People who want more control and plan to build bigger projects later |

> 💡 **Not sure which to pick?** Go with **Path A** (Lovable). You can always try Path B later. The important thing right now is to **build something and feel the magic.**

---

## Path A: Build with Lovable (No Install Needed)

### What You'll Need
- A computer with a web browser (Chrome, Firefox, Safari, Edge — any will work)
- An email address or Google account for signing up
- About 30 minutes of your time

That's it. No downloads. No installations. No terminal. Let's go.

---

### Step 1: Sign Up at Lovable

1. Open your browser and go to **[lovable.dev](https://lovable.dev)**
2. Click **"Get Started"** or **"Sign Up"**
3. Sign in with your Google account, or create an account with your email
4. You'll land on the Lovable dashboard — a clean interface with a text box waiting for your instructions

✅ **What you should see:** A welcoming dashboard with an area to describe your project.

> 🤔 **Feeling nervous?** That's completely normal. Everyone feels a little "is this really going to work?" the first time. Spoiler: it really works.

---

### Step 2: Describe Your App

This is where the magic happens. In the text box, type this prompt (feel free to customize it with your own name and details):

```
Build me a personal portfolio website with the following sections:

1. Hero section at the top with:
   - My name: "Alex Johnson" (use a large, bold heading)
   - Tagline: "Designer, creator, and problem solver"
   - A brief intro paragraph: "I help businesses turn ideas into beautiful digital experiences."
   - A "Get in Touch" button that scrolls to the contact form

2. About Me section with:
   - A short bio (2-3 paragraphs about being a creative professional)
   - A grid of skills/tools I use (Design, Strategy, Branding, Web Design, Photography, Marketing)

3. Projects section with:
   - A gallery grid showing 4 project cards
   - Each card has a project image placeholder, title, short description, and a "View Project" link
   - Use sample project names: "Brand Refresh for Bloom Co", "E-commerce Redesign", "Mobile App UI", "Marketing Campaign"

4. Contact section with:
   - A heading: "Let's Work Together"
   - A contact form with fields for Name, Email, and Message
   - A "Send Message" button

Design preferences:
- Clean, modern, minimal design
- Color scheme: white background with navy blue (#1e3a5f) accents
- Use a sans-serif font
- Make it responsive (looks good on phones too)
- Add smooth scroll behavior
```

Click **Send** or press **Enter**.

---

### Step 3: Watch AI Build Your App

Now sit back and watch. Lovable will:

1. **Understand your description** — it reads your prompt and plans the structure
2. **Generate the code** — you'll see files being created in real-time
3. **Show a live preview** — your app appears on the right side of the screen

This usually takes **30–90 seconds**. You'll see progress indicators as it works.

✅ **What you should see:** A live preview of your portfolio website on the right side of the screen. It should have all four sections you described.

> 🎉 **Take a moment.** You just built a website by *describing* what you wanted. No code. No tutorials. No months of learning. Just a conversation.

---

### Step 4: Iterate and Improve

Your first version probably looks good, but it might not be *exactly* right. That's totally normal — even professional designers go through rounds of revision.

Here's the fun part: you can just **tell Lovable what to change**, and it'll update instantly.

Try typing these follow-up prompts one at a time:

**Change 1 — Add a dark mode toggle:**
```
Add a dark mode toggle button in the top-right corner of the navigation bar.
When toggled, the entire site should switch to a dark color scheme
(dark navy background, white text). Remember the user's preference.
```

**Change 2 — Improve the hero section:**
```
Make the hero section full-height (takes up the entire screen when you first
land on the page). Add a subtle gradient background from white to light blue.
Add a gentle fade-in animation when the page loads.
```

**Change 3 — Make the project cards interactive:**
```
When hovering over a project card, add a slight zoom effect and a shadow.
Make the cards feel clickable and interactive.
```

**Change 4 — Add a navigation bar:**
```
Add a sticky navigation bar at the top with links to each section:
Home, About, Projects, Contact. The nav bar should be transparent at the
top but get a white background when you scroll down.
```

After each prompt, review the preview. Does it look right? If not, just describe what's off:

- *"The text is too small on the hero section — make it bigger"*
- *"I don't like the blue, change it to forest green (#2d5a3d)"*
- *"The contact form is too wide — make it narrower, about half the page width"*

This back-and-forth is the heart of vibe coding. **You're having a conversation with AI, and together you're building an app.**

---

### Step 5: Deploy Your App (Go Live!)

Your portfolio looks great. Now let's put it on the internet so anyone can see it.

1. Look for a **"Publish"** or **"Deploy"** button (usually in the top-right area)
2. Click it
3. Lovable will give you a **live URL** — something like `https://your-project-name.lovable.app`
4. **Open that URL in a new tab** to see your live website
5. **Share the link** with a friend, post it on social media, or send it to a potential client

✅ **What you should see:** Your portfolio website, live on the internet, accessible to anyone with the link.

> 💡 **Want a custom domain?** (like `alexjohnson.com`) You can connect one later — we'll cover that in [Chapter 15: Deploying Your App](../15-deploying/). For now, the free Lovable URL works perfectly.

---

### 🎉 You Did It! (Path A Complete)

**Congratulations!** You just built and deployed a real website. Not a tutorial exercise. Not a mockup. A *real*, live website that anyone on the internet can visit.

Take a screenshot. Share it with someone. Celebrate this moment — most people never get past "I wish I could build an app."

**You just did.**

Skip ahead to the [What You Learned](#-what-you-learned) section below.

---

## Path B: Build with Cursor (More Control)

### What You'll Need
- A computer (Windows, Mac, or Linux)
- Cursor installed (see [Chapter 2](../02-choosing-your-tools/) for setup instructions)
- About 30 minutes of your time

This path gives you more control over the project files and structure. It's a bit more involved, but it prepares you for building bigger, more complex apps later.

---

### Step 1: Download and Open Cursor

If you haven't already:
1. Go to [cursor.com](https://cursor.com) and download the app
2. Install it (just like installing any other program)
3. Open Cursor

**Don't panic** when you see the interface. It looks like a professional code editor with lots of panels and buttons. You'll mostly be using just one thing: the **AI chat panel**.

---

### Step 2: Create a New Project

1. Go to **File → Open Folder**
2. Create a new folder on your computer called `my-portfolio` (put it anywhere you like — your Desktop or Documents folder is fine)
3. Select that folder and click **Open**

You should now see an empty project in Cursor's sidebar.

---

### Step 3: Open the AI Chat and Describe Your App

1. Press **`Ctrl+L`** on Windows or **`Cmd+L`** on Mac to open the AI chat panel
2. You should see a chat interface on the right side of the screen

Now, type this prompt:

```
Create a personal portfolio website for me. I want a single-page site using
HTML, CSS, and vanilla JavaScript (no frameworks needed). The page should include:

1. A navigation bar at the top with links: Home, About, Projects, Contact
   - Make it sticky so it stays visible when scrolling

2. A hero section with:
   - Name: "Alex Johnson" in large bold text
   - Tagline: "Designer, creator, and problem solver"
   - A short intro: "I help businesses turn ideas into beautiful digital experiences."
   - A "Get in Touch" button that scrolls to the contact section

3. An About section with:
   - A short bio (2-3 paragraphs)
   - A skills grid showing: Design, Strategy, Branding, Web Design, Photography, Marketing

4. A Projects section with:
   - 4 project cards in a grid layout
   - Each card: placeholder image area, project title, short description
   - Project names: "Brand Refresh for Bloom Co", "E-commerce Redesign", "Mobile App UI", "Marketing Campaign"
   - Hover effect: slight zoom and shadow

5. A Contact section with:
   - Heading: "Let's Work Together"
   - A form with Name, Email, Message fields and a Send button

Design:
- Clean, modern, minimal
- Color scheme: white background with navy (#1e3a5f) accents
- Sans-serif font (use system fonts)
- Fully responsive (works on mobile)
- Smooth scrolling

Please create an index.html file with everything included (inline CSS and JS
is fine for this project).
```

Press **Enter** or click **Send**.

---

### Step 4: Review What AI Generated

Cursor will create a file called `index.html` in your project. You'll see the code appear in the editor. Here's what to do:

1. **Click "Accept"** or **"Apply"** if Cursor asks you to confirm the changes
2. **Find the file** in the left sidebar — click on `index.html`
3. **Preview it:** Right-click the file and look for "Open in Browser," or:
   - On Windows: Open File Explorer, navigate to your `my-portfolio` folder, and double-click `index.html`
   - On Mac: Open Finder, navigate to your `my-portfolio` folder, and double-click `index.html`
   - It will open in your default web browser

✅ **What you should see:** Your portfolio website displayed in your browser. It's running locally (only on your computer for now), but it's real and working!

---

### Step 5: Iterate Using Chat

Just like with Lovable, you can ask Cursor to make changes. Go back to the chat panel (`Ctrl+L` / `Cmd+L`) and try these:

**Add dark mode:**
```
Add a dark mode toggle button in the top-right corner of the nav bar.
When clicked, the site should switch to a dark theme (dark background, light text).
Save the user's preference in localStorage so it persists between visits.
```

**Improve animations:**
```
Add these animations:
- Fade-in effect for each section as the user scrolls down
- Smooth hover transitions on project cards (0.3s ease)
- The hero section should have a gentle fade-in when the page first loads
```

**Make the nav smarter:**
```
Highlight the current section in the navigation bar as the user scrolls.
For example, when the user is viewing the "About" section, the "About"
link in the nav should be highlighted with an underline or different color.
```

After each change, refresh your browser to see the updates. If something doesn't look right, just tell Cursor:

- *"The dark mode toggle is in the wrong position — move it to the far right of the nav bar"*
- *"The animations are too fast — slow them down"*
- *"The mobile layout is broken — the project cards are overlapping. Fix the grid for small screens"*

---

### Step 6: Deploy to Vercel

Your app works locally. Now let's put it on the internet.

**Vercel** is a free hosting platform that makes deployment incredibly easy. Here's how:

1. **Go to** [vercel.com](https://vercel.com) and sign up with your GitHub account
   - Don't have a GitHub account? Create one at [github.com](https://github.com) — it's free and takes 2 minutes
2. **Install the Vercel CLI** (command-line tool):
   - In Cursor, open the terminal: **View → Terminal** (or press `` Ctrl+` ``)
   - You'll see a text area at the bottom of the screen — this is the terminal
   - Type: `npm install -g vercel` and press Enter
   - Wait for it to finish (you might see some progress text)
3. **Deploy your project:**
   - In the same terminal, type: `vercel` and press Enter
   - Vercel will ask a few questions — you can press Enter for all of them to accept defaults
   - It will upload your files and give you a **live URL**
4. **Open your URL** in a new browser tab

✅ **What you should see:** Your portfolio website, live on the internet at a URL like `https://my-portfolio-abc123.vercel.app`

> 💡 **Don't have Node.js installed?** The `npm` command above requires Node.js. Download it from [nodejs.org](https://nodejs.org) — grab the "LTS" version. Install it, restart Cursor, and try again.

> 💡 **Alternative: Drag and drop.** If the terminal feels overwhelming, you can also go to [vercel.com/new](https://vercel.com/new), click "Import Project," and drag your entire project folder onto the page. Vercel will deploy it automatically.

---

### 🎉 You Did It! (Path B Complete)

**Congratulations!** You built a portfolio website using a professional-grade editor, and you deployed it to the internet. You've taken a path that gives you more control — and that's going to pay off big time as you build more complex apps.

---

## 🧠 What You Learned

Take a moment to appreciate what just happened. In about 30 minutes, you:

| What You Did | Why It Matters |
|---|---|
| ✅ Described an app in plain English | You learned that building software starts with **clear communication**, not code |
| ✅ Reviewed and gave feedback to AI | You practiced the **iterate-and-improve** loop that's at the heart of vibe coding |
| ✅ Made design decisions | You acted as the **architect** — choosing colors, layouts, and features |
| ✅ Deployed to the internet | You learned that **shipping** is not some scary, complex process |
| ✅ Built a real, working website | You proved to yourself that **you can do this** |

These five skills — describing, reviewing, deciding, deploying, and shipping — are the same skills you'll use whether you're building a personal portfolio or a SaaS app with 10,000 users. The scale changes, but the process stays the same.

---

## 💡 Ideas to Keep Practicing

Not ready to move on? Here are some quick projects to practice with:

### Project 2: A Landing Page for a Fake Product
```
Build a landing page for a product called "FocusFlow" — an AI-powered
productivity app. Include a hero section with headline and CTA, a features
section with 3 features (icons + descriptions), a pricing section with
3 tiers (Free, Pro, Enterprise), and a footer with social links.
```

### Project 3: A Simple To-Do App
```
Build a to-do list app where users can:
- Add new tasks with a text input and "Add" button
- Mark tasks as complete (with a checkbox or strikethrough)
- Delete tasks
- Tasks should persist in the browser (use localStorage)
Use a clean, minimal design with a calming color palette.
```

### Project 4: A Restaurant Menu Page
```
Build a digital menu for a restaurant called "The Garden Kitchen."
Include categories: Starters, Mains, Desserts, Drinks. Each item
should have a name, short description, and price. Add a vegetarian/vegan
filter toggle at the top. Make it look warm and inviting.
```

Each of these can be built in 15–20 minutes. The more you practice, the better you'll get at describing what you want — and that's the most valuable skill in vibe coding.

---

## Troubleshooting Common Issues

### "The AI didn't build what I described"
This usually means the prompt needs more detail. Instead of "make it look good," try "use a white background, navy blue headings, and rounded corners on all cards." The more specific you are, the better the result. We'll dive deep into this in [Chapter 4: Prompting 101](../04-prompting-101/).

### "I see an error message"
Don't panic. Copy the exact error message and paste it back to the AI: "I'm getting this error: [paste error]. How do I fix it?" AI is *great* at debugging its own code.

### "The site looks broken on mobile"
Tell the AI: "The layout is broken on mobile devices. The [describe what's wrong — e.g., 'cards are overlapping' or 'text is too small']. Please fix the responsive design." AI understands responsive design well and can usually fix it in one prompt.

### "I can't deploy / the deploy button isn't working"
For Lovable/Bolt: Try refreshing the page and clicking deploy again. If it persists, check that you haven't hit your free tier limit for the day.
For Cursor/Vercel: Make sure you're signed in to Vercel and that Node.js is installed. The terminal error message usually tells you exactly what's wrong — paste it into the AI chat for help.

### "I accidentally broke something and want to go back"
Most tools have an **undo** function or **version history**:
- **Lovable/Bolt:** Look for a history or version panel — you can revert to a previous state
- **Cursor:** Press `Ctrl+Z` / `Cmd+Z` to undo, or use Git (we'll cover this in later chapters)

---

## What's Next?

You've proven to yourself that you can build real apps with AI. That was the hardest step — going from "I can't code" to "I just built something."

But you probably noticed that the quality of what AI builds depends a lot on **how you describe what you want**. Sometimes it nails it on the first try; sometimes it misses the mark.

In the next chapter, we're going to fix that. You'll learn **Prompting 101** — how to write descriptions that get great results consistently. This is the single most important skill in vibe coding, and it'll make everything from here on easier.

**See you in Chapter 4! 🚀**

---

[← Previous: Choosing Your Tools](../02-choosing-your-tools/) · [Back to Playbook](../../README.md) · [Next: Prompting 101 →](../04-prompting-101/)
