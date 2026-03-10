# 📖 Glossary

> Tech jargon can feel like a foreign language. This glossary translates the most common terms you'll encounter into plain, friendly English. Bookmark this page — you'll come back to it often!

---

### API (Application Programming Interface)

A way for two pieces of software to talk to each other. Think of it like a waiter at a restaurant: you (your app) tell the waiter (the API) what you want, the waiter takes your order to the kitchen (the other service), and brings back your food (the data). For example, when your app gets weather data, it's using a weather API.

### API Key

A secret password that identifies your app when it talks to an API. It's like a membership card — the API checks your key to make sure you're allowed in and to track your usage. **Keep your API keys secret!** Never put them directly in your code. Use environment variables instead.

### Authentication (Auth)

The process of proving who you are — logging in, basically. When a user enters their email and password, that's authentication. Common auth methods include email/password, Google sign-in, and magic links.

### Backend

The behind-the-scenes part of your app that users never see. It handles things like storing data, processing payments, sending emails, and talking to APIs. If your app were a restaurant, the backend is the kitchen.

### Build

The process of converting your human-readable code into a version that can run on the internet. When you "build" your app, the computer bundles, optimizes, and prepares your code for deployment. Build errors mean something went wrong during this process.

### CLI (Command Line Interface)

A text-based way to interact with your computer by typing commands instead of clicking buttons. It looks like a black screen with a blinking cursor (think: the hacker scenes in movies). Intimidating at first, but you'll only need a handful of commands. Also called the "terminal."

### Component

A reusable building block of your user interface. A button is a component. A navigation bar is a component. A card showing a product is a component. You build them once and use them everywhere — like LEGO bricks.

### CSS (Cascading Style Sheets)

The language that controls how your app LOOKS — colors, fonts, spacing, layouts, animations. HTML is the skeleton, CSS is the skin and clothing. Tailwind CSS is a popular tool that makes writing CSS faster and easier.

### Database

Where your app stores information permanently. User accounts, blog posts, product listings, orders — all of that lives in a database. Think of it as a super-organized spreadsheet that your app can read and write to automatically. Popular options include Supabase (PostgreSQL), Firebase, and PlanetScale.

### Dependencies

Other people's code that your app relies on. Instead of building everything from scratch, you use pre-built packages (like LEGO sets) for common tasks — handling dates, sending emails, processing payments, etc. These are managed by tools like npm.

### Deploy / Deployment

The act of putting your app on the internet so other people can use it. When you "deploy," you take the code on your computer and publish it to a hosting service (like Vercel or Netlify). After deploying, anyone with the URL can visit your app.

### DNS (Domain Name System)

The internet's phone book. It translates human-friendly domain names (like "google.com") into computer-friendly IP addresses (like "142.250.80.46"). When you connect a custom domain to your app, you're updating DNS records.

### Endpoint

A specific URL that your backend listens on. For example, `yourapp.com/api/users` might be an endpoint that returns a list of users. Think of endpoints as different doors into your backend — each one handles a specific type of request.

### Environment Variable (Env Var)

A secret value stored OUTSIDE your code — like API keys, database passwords, or configuration settings. They're different for each environment (your computer vs. the live site). You set them in your hosting platform's dashboard. They keep your secrets safe.

### Framework

A pre-built structure for building apps, like a blueprint for a house. Instead of starting from an empty file, frameworks give you a organized starting point with common features already set up. Examples: Next.js, React, Astro, Express.

### Frontend

The part of your app that users see and interact with — buttons, text, images, forms, navigation. If your app were a restaurant, the frontend is the dining room. Built with HTML, CSS, and JavaScript.

### Full-Stack

An app (or developer) that covers both the frontend AND the backend. A "full-stack app" has a user interface AND a server/database. Many modern tools (like Next.js + Supabase) make it possible to build full-stack apps by yourself.

### Git

A tool that tracks every change you make to your code, like "Track Changes" in Google Docs but way more powerful. It lets you save snapshots of your work, go back to previous versions, and collaborate with others without overwriting each other's work.

### GitHub

A website where you store your Git repositories (your code projects) online. It's like Google Drive for code. It also powers collaboration, deployment, and version history. Free for public and private projects.

### Hosting

The service that runs your app on the internet 24/7. Your code needs to live on a computer that's always on and always connected — that's what hosting provides. Vercel, Netlify, and Railway are popular hosting platforms with free tiers.

### HTML (HyperText Markup Language)

The language that defines the STRUCTURE of a web page — headings, paragraphs, images, links, forms. It's the skeleton of every web page. HTML tells the browser WHAT to show; CSS tells it HOW to look; JavaScript tells it WHAT to do.

### HTTP / HTTPS

The language that web browsers and servers use to talk to each other. HTTPS is the secure version (the "S" stands for "Secure"). That little padlock icon in your browser's address bar means the site uses HTTPS. Always use HTTPS — it's free on modern hosting platforms.

### IDE (Integrated Development Environment)

A fancy name for a code editor with superpowers — code highlighting, error detection, file management, built-in terminal, and more. VS Code is the most popular free IDE. Cursor is a VS Code-based IDE with built-in AI features.

### JavaScript (JS)

The programming language of the web. It makes web pages interactive — clicking buttons, loading data, animations, form validation, and much more. Every web browser can run JavaScript. When you vibe code, most of the code AI generates will be JavaScript (or TypeScript).

### JSON (JavaScript Object Notation)

A simple format for storing and sending data, like a very structured text file. It uses curly braces and key-value pairs: `{"name": "Sarah", "age": 30}`. APIs almost always send and receive data as JSON. You'll see it everywhere.

### LLM (Large Language Model)

The AI technology behind tools like ChatGPT and Claude. It's a program trained on massive amounts of text that can understand and generate human language — including code. When you "talk to AI" to build your app, you're talking to an LLM.

### Localhost

Your own computer acting as a temporary server while you're building your app. When you "run your app locally," it's only visible to you at an address like `http://localhost:3000`. Nobody else on the internet can see it until you deploy.

### MCP (Model Context Protocol)

A standard way to give AI tools access to external data and services. Think of it as a universal plug that lets your AI assistant connect to databases, APIs, file systems, and other tools so it can do more than just chat — it can actually take actions and access real information.

### Middleware

Code that runs BETWEEN a request coming in and a response going out. Think of it as a security checkpoint at an airport — it checks things (is the user logged in? is the request valid?) before letting the request through to its destination.

### Migration

A controlled change to your database structure. When you need to add a new column (like "phone number" to your users table), you write a migration. It's like a careful, reversible set of instructions for modifying your database without losing data.

### MVP (Minimum Viable Product)

The simplest possible version of your app that still solves the core problem. It's NOT a crappy version — it's a focused version. Build only the features that matter most, launch, get feedback, then add more. This is the most important concept for solopreneurs.

### Node.js

A way to run JavaScript outside of a web browser — on a server, on your computer, anywhere. Most modern web apps use Node.js for their backend. When you install packages with npm, you're using Node.js.

### npm (Node Package Manager)

A tool for installing and managing JavaScript packages (pre-built code libraries). When a tutorial says "run `npm install`," it's downloading all the dependencies your project needs. Think of it as an app store for code packages.

### ORM (Object-Relational Mapping)

A tool that lets you interact with your database using your programming language instead of writing raw database queries. Instead of writing `SELECT * FROM users WHERE id = 1`, you write something like `User.findById(1)`. Prisma and Drizzle are popular ORMs.

### Package

A bundle of pre-written code that does something specific — like handling dates, sending emails, or resizing images. Packages save you from reinventing the wheel. You install them with npm and use them in your project.

### Prompt

The instruction or question you give to an AI tool. A good prompt is specific, provides context, and clearly states what you want. Prompting is the core skill of vibe coding — the better your prompts, the better your results.

### PR (Pull Request)

A way to propose changes to code on GitHub. You make changes in a separate "branch," then open a pull request saying "hey, I'd like to merge these changes into the main code." It's a review and discussion step before changes go live.

### PWA (Progressive Web App)

A web app that can be installed on your phone like a regular app — with an icon on the home screen, offline support, and push notifications. It's built with web technology but feels native. A great way to get your app on phones without dealing with app stores.

### Query

A request for specific data from a database. "Give me all users who signed up this month" is a query. "Find all orders over $100" is a query. In code, queries are often written in SQL or through an ORM.

### React

A popular JavaScript library for building user interfaces, created by Meta (Facebook). It lets you build your app as a collection of reusable components. The most widely-used UI library in the world, so AI tools are exceptionally good at writing React code.

### Repository (Repo)

A folder for your project that's tracked by Git. It contains your code, its full history, and configuration files. When people say "push to your repo," they mean upload your latest code changes to GitHub. Every project should have its own repository.

### REST API

A standard way to design APIs using URLs and HTTP methods. `GET /api/users` fetches users. `POST /api/users` creates a user. `DELETE /api/users/5` deletes user #5. Most web APIs follow REST conventions, and AI tools know them inside and out.

### Route

A URL path in your app that shows a specific page or handles a specific request. `/about` is a route that shows the About page. `/api/login` is a route that handles login requests. Routing is how your app knows which page to show based on the URL.

### SaaS (Software as a Service)

A software product that people pay to use, usually through a monthly or yearly subscription. Think Netflix, Slack, or Notion. If you build an app that charges users a recurring fee, you've built a SaaS. This is the most popular business model for solopreneur apps.

### Server

A computer that's always on and connected to the internet, running your app so people can use it. When you deploy to Vercel or Railway, your code runs on their servers. You don't need to own a server — hosting platforms handle this for you.

### Serverless

A way of running backend code without managing a server yourself. Your code runs only when it's needed and scales automatically. Vercel and Netlify use serverless functions. Despite the name, there ARE servers — you just don't have to think about them.

### SSL/TLS Certificate

The technology that makes HTTPS work — it encrypts data between your users' browsers and your server. That padlock icon in the browser bar? That's SSL. Modern hosting platforms give you free SSL certificates automatically.

### Supabase

An open-source alternative to Firebase. It gives you a PostgreSQL database, user authentication, file storage, and real-time features — all from one dashboard. Very popular in the vibe coding community because it's powerful, has a generous free tier, and AI tools know it well.

### Tailwind CSS

A CSS framework that lets you style your app using small, pre-built utility classes directly in your HTML. Instead of writing separate CSS files, you write classes like `text-blue-500 font-bold p-4`. AI tools are extremely good at writing Tailwind code, making it the go-to choice for vibe coders.

### Terminal

The application on your computer where you type commands (also called the command line, console, or shell). On Mac it's called Terminal, on Windows it's PowerShell or Command Prompt. It looks like a black screen with text. You'll use it to run your app, install packages, and deploy.

### Token

In AI context: the unit that LLMs use to process text. Roughly, 1 token ≈ ¾ of a word. AI tools charge based on tokens used. In authentication context: a piece of data (like a temporary password) that proves a user is logged in, so they don't have to enter their password on every page.

### TypeScript (TS)

JavaScript with added safety features. It lets you define what type of data each variable should hold (text, number, list, etc.), catching mistakes before your app runs. Most modern projects use TypeScript. Don't be intimidated — AI handles the TypeScript details for you.

### UI (User Interface)

Everything the user sees and interacts with on screen — buttons, menus, forms, text, images, icons, colors. When someone says "the UI looks great," they mean the visual design and layout of the app are well done.

### URL (Uniform Resource Locator)

A web address, like `https://www.google.com/search?q=hello`. Every page and resource on the internet has a URL. Your deployed app gets a URL (like `myapp.vercel.app`), and you can connect a custom domain to make it prettier.

### UX (User Experience)

How it FEELS to use your app — not just how it looks, but how easy, intuitive, and pleasant the experience is. Good UX means users can accomplish their goals without frustration. It covers navigation flow, loading speed, error handling, accessibility, and more.

### Vercel

A hosting platform especially popular for Next.js and React apps. Known for its simplicity — connect your GitHub repo and it auto-deploys every time you push code. Has a generous free tier. One of the most popular choices for solopreneur app deployment.

### Version Control

A system for tracking changes to your code over time. Git is the most popular version control tool. It lets you save snapshots (commits), go back in time, create separate branches for experiments, and collaborate safely. Essential from day one — don't skip this.

### Webhook

A way for one app to notify another app when something happens. Like a doorbell — when an event occurs (a payment is made, a form is submitted), the webhook "rings" your app's URL to let it know. Stripe uses webhooks to tell your app when a payment succeeds.

---

## 💡 Didn't Find a Term?

Ask your AI assistant! Try: "Explain [term] to me like I'm a complete beginner with no coding experience. Use an everyday analogy."

Or suggest additions to this glossary by contributing to the playbook.

---

*Part of [The Vibe Coding Playbook](../README.md) — a guide for building real apps with zero coding experience.*
