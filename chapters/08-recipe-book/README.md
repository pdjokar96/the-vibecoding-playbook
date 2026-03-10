# Chapter 8: Common Builds — Recipe Book 🍳

You know those cookbooks where every recipe has been tested a dozen times before it made it to the page? That's what this chapter is. These are **six proven recipes** — step-by-step builds that real people ship every day using AI coding tools.

## How to Use This Recipe Book

Each recipe follows the same format so you always know what to expect:

1. **Read the overview** — understand *what* you're building and *why* it matters.
2. **Check the tools and difficulty** — make sure you have what you need before you start.
3. **Follow the prompts in order** — each prompt builds on the last. Copy-paste them exactly, then tweak the details (your brand name, your colors, your words).
4. **Check the "Expected Result"** after each step — this tells you what you should see on screen so you know you're on track.

> 💡 **Tip:** Don't try to build everything in one giant prompt. These recipes break the work into small, manageable pieces on purpose. Each step gives the AI a clear, focused job — and that's how you get the best results.

> 🔁 **If something looks off**, don't panic. Just tell the AI what's wrong in plain English: *"The button is too small"* or *"Move the testimonials below the features section."* That's the beauty of vibe coding — you're having a conversation, not writing code.

Let's build some real things.

---

## Recipe 1: SaaS Landing Page with Waitlist

**What you're building:** A professional landing page for your software product idea — the kind that collects email addresses from people who want early access. Think of it as your digital storefront before the store is even open.

**Why it matters:** A landing page is the fastest way to validate whether anyone actually wants what you're building. Before you spend weeks (or months) on a product, put up a page and see if people sign up. If they do, you're onto something.

- ⏱ **Time estimate:** 30–45 minutes
- 📊 **Difficulty:** Beginner
- 🛠 **Tools:** [Bolt](https://bolt.new), [Lovable](https://lovable.dev), or [v0](https://v0.dev)

### Step 1 — Create the Hero Section

This is the very first thing visitors see. It needs to grab attention in about three seconds.

```
Build a modern SaaS landing page hero section. Include a bold headline that says
"Stop Guessing, Start Growing" and a subheadline underneath that says "The AI-powered
analytics tool that turns your messy data into clear next steps — no spreadsheets
required." Add a large email input field with placeholder text "Enter your email" and
a bright call-to-action button that says "Join the Waitlist." Use a clean, modern
design with a gradient background that goes from dark blue to purple. Make the text
white and center everything on the page.
```

✅ **Expected result:** A full-width hero section with a bold headline, a subtitle, an email input box, and a colorful button — all centered and looking polished.

### Step 2 — Add the Features Grid

Now show visitors *why* your product is worth waiting for.

```
Below the hero section, add a features section with the heading "Why Teams Love Us."
Create a grid of 4 feature cards. Each card should have an icon, a short title, and
a one-sentence description. The four features are:
1. Lightning bolt icon — "Real-Time Insights" — "See what's happening in your
   business right now, not last week."
2. Shield icon — "Bank-Level Security" — "Your data is encrypted and never shared
   with third parties."
3. Chart icon — "One-Click Reports" — "Generate beautiful reports you can share
   with your team in seconds."
4. Users icon — "Built for Teams" — "Collaborate with your whole crew — no extra
   cost per seat."
Use a white background for this section to contrast with the hero. Cards should have
subtle shadows and rounded corners.
```

✅ **Expected result:** Four clean cards in a grid (2×2 on desktop, stacked on mobile) with icons, titles, and short descriptions.

### Step 3 — Add Social Proof with Testimonials

People trust other people more than they trust your marketing copy. Let's add some voices.

```
Below the features section, add a testimonials section with the heading "What Early
Users Are Saying." Show 3 testimonial cards side by side. Each card should have a
quote in italics, a person's name in bold, and their role and company underneath.
Use these testimonials:
1. "This replaced three tools we were paying for. Absolute game-changer." — Sarah
   Kim, Head of Growth at Launchpad Co.
2. "I finally understand our numbers. The reports basically write themselves." —
   Marcus Johnson, Founder of BrightPath
3. "Setup took five minutes. Five. Minutes." — Priya Patel, Operations Lead at
   NovaTech
Add small circular avatar placeholders next to each name. Use a light gray background
for this section.
```

✅ **Expected result:** Three testimonial cards with quotes, names, roles, and placeholder avatars — arranged in a row on desktop and stacked on mobile.

### Step 4 — Add a Final Call-to-Action

Visitors who scroll all the way down are interested. Give them one more chance to sign up.

```
Add a final call-to-action section at the bottom of the page, before the footer. Use
a bold background color (the same gradient from the hero). Include the headline
"Ready to See Your Data Clearly?" and a subheadline "Join 2,000+ teams on the
waitlist. We launch in Spring 2025." Add another email input field and "Get Early
Access" button, styled the same as the hero. Below the button, add small text that
says "No spam, ever. Unsubscribe anytime."
```

✅ **Expected result:** A visually striking bottom section that mirrors the hero, giving visitors a second opportunity to enter their email.

### Step 5 — Make the Waitlist Actually Work

A form that doesn't save emails is just decoration. Let's connect it.

```
Make both email signup forms functional. When someone enters their email and clicks
the button, save the email to local storage and show a success message that says
"You're on the list! 🎉 We'll be in touch soon." Replace the form with the success
message after submission. Also add basic email validation — if someone submits an
empty field or an email without an @ symbol, show a red error message that says
"Please enter a valid email address."
```

> 💡 **Tip:** Local storage works great for a demo or MVP. When you're ready for the real thing, you can swap it out for a service like [Mailchimp](https://mailchimp.com), [ConvertKit](https://convertkit.com), or a simple database. Just tell the AI: *"Replace the local storage with a ConvertKit form integration."*

✅ **Expected result:** Entering a valid email and clicking the button shows a success message. Entering a bad email shows an error. Emails are stored in the browser's local storage.

### Step 6 — Add a Navigation Bar and Footer

Finish it off with a professional top and bottom.

```
Add a sticky navigation bar at the top with the logo text "DataLens" on the left and
links for "Features," "Testimonials," and "Join Waitlist" on the right. When clicked,
each link should smooth-scroll to that section of the page. Add a simple footer at
the bottom with "© 2025 DataLens. All rights reserved." centered, and links to
"Privacy Policy" and "Terms of Service" (these can be placeholder links for now).
Make the navbar transparent when at the top of the page and give it a solid white
background with a subtle shadow when the user scrolls down.
```

✅ **Expected result:** A polished nav bar that changes appearance on scroll, smooth scrolling to each section, and a clean footer. Your landing page is done!

---

## Recipe 2: Personal Dashboard

**What you're building:** A personal dashboard — a single page where you can see your important stats, progress, and info at a glance. Think of it like the home screen of your phone, but for your data.

**Why it matters:** Dashboards teach you a ton about layout, data display, and responsive design. They're also genuinely useful — you can track your business metrics, habits, goals, or anything else you care about.

- ⏱ **Time estimate:** 25–35 minutes
- 📊 **Difficulty:** Beginner
- 🛠 **Tools:** [Bolt](https://bolt.new) or [Lovable](https://lovable.dev)

### Step 1 — Build the Layout Shell

Every dashboard starts with a skeleton — the sidebar and main area.

```
Create a personal dashboard layout with a dark sidebar on the left and a light main
content area on the right. The sidebar should have a user avatar placeholder at the
top, then navigation links for "Overview," "Analytics," "Tasks," and "Settings." Add
a small "Log Out" link at the bottom of the sidebar. At the top of the main content
area, add a header that says "Good morning, Alex 👋" with today's date shown below
it in a smaller font. On mobile, the sidebar should collapse into a hamburger menu.
```

✅ **Expected result:** A two-column layout with a dark sidebar and a light main area. On mobile, the sidebar hides behind a menu icon.

### Step 2 — Add Stat Cards

Now fill the main area with quick-glance numbers.

```
In the main content area below the greeting, add a row of 4 stat cards. Each card
should display a metric label, a large number, and a small percentage showing change
from last month (with a green up arrow or red down arrow). The four cards are:
1. "Total Revenue" — "$12,480" — "+14% from last month" (green, up arrow)
2. "Active Users" — "1,247" — "+8% from last month" (green, up arrow)
3. "Tasks Completed" — "38" — "-3% from last month" (red, down arrow)
4. "Support Tickets" — "5" — "+2% from last month" (red, down arrow)
Cards should have white backgrounds, rounded corners, and subtle shadows. They should
stack in two rows of two on mobile.
```

✅ **Expected result:** Four stat cards with numbers and colored trend indicators, responsive across screen sizes.

### Step 3 — Add Charts and Progress Bars

Visuals make data click. Let's add some.

```
Below the stat cards, add two sections side by side. On the left, create a simple bar
chart showing "Weekly Revenue" for the last 7 days with these values: Mon $320,
Tue $480, Wed $290, Thu $520, Fri $680, Sat $410, Sun $350. Use a blue color for
the bars. On the right, add a "Goals Progress" section with 3 progress bars:
1. "Monthly Revenue Goal" — 74% complete (blue bar)
2. "New Users Target" — 62% complete (green bar)
3. "Content Published" — 90% complete (purple bar)
Each progress bar should show the percentage number at the right end. Both sections
should stack vertically on mobile screens.
```

✅ **Expected result:** A bar chart on the left and three color-coded progress bars on the right, both responsive.

### Step 4 — Add a Recent Activity Feed

Give users a sense of what's been happening lately.

```
Below the charts, add a "Recent Activity" section that shows a feed of the last 5
activities. Each activity item should have a small colored dot on the left (like a
timeline), a description in the middle, and a timestamp on the right. Use these
activities:
1. Green dot — "New user signed up: jamie@example.com" — "2 minutes ago"
2. Blue dot — "Invoice #1042 paid — $299.00" — "1 hour ago"
3. Yellow dot — "Support ticket opened by customer" — "3 hours ago"
4. Green dot — "Blog post 'Getting Started Guide' published" — "Yesterday"
5. Blue dot — "Monthly report generated" — "2 days ago"
Style it as a clean vertical timeline with subtle connecting lines between the dots.
```

✅ **Expected result:** A vertical timeline-style activity feed with colored dots, descriptions, and relative timestamps. Your dashboard is complete!

---

## Recipe 3: Stripe Payment Integration

**What you're building:** A checkout page that accepts real credit card payments using Stripe. This is the thing that turns your project from a hobby into a business — the moment money can change hands.

**Why it matters:** Getting paid is the whole point. Stripe is the most popular payment system for online businesses, and once you understand the pattern, you can add payments to any project.

- ⏱ **Time estimate:** 45–60 minutes
- 📊 **Difficulty:** Intermediate
- 🛠 **Tools:** [Cursor](https://cursor.sh) or [Bolt](https://bolt.new) + [Stripe Docs](https://stripe.com/docs)

> ⚠️ **Before you start:** You'll need a free [Stripe account](https://dashboard.stripe.com/register). Once you sign up, grab your **test mode API keys** from the Stripe Dashboard (Developers → API Keys). Test mode means no real money moves — you can practice safely.

### Step 1 — Create the Pricing Page

Show visitors what they can buy.

```
Build a pricing page with 3 pricing tiers displayed as cards side by side. Make the
middle card slightly larger and highlighted as "Most Popular" with a colored border.
The three tiers are:
1. "Starter" — $9/month — Features: "1 project," "Basic analytics," "Email support"
   — Button says "Get Started"
2. "Pro" (highlighted) — $29/month — Features: "10 projects," "Advanced analytics,"
   "Priority support," "Custom domain" — Button says "Go Pro"
3. "Enterprise" — $79/month — Features: "Unlimited projects," "Full analytics suite,"
   "24/7 phone support," "API access," "Dedicated manager" — Button says "Contact Us"
Add a toggle at the top that switches between monthly and annual pricing (annual
should show a 20% discount). Use a clean, professional design.
```

✅ **Expected result:** Three pricing cards with a monthly/annual toggle. The middle card stands out visually. Each card has a clear list of features and a button.

### Step 2 — Set Up the Backend for Stripe

Now wire up the server that talks to Stripe.

```
Create a Node.js Express server with a POST endpoint at /create-checkout-session.
This endpoint should use the Stripe Node.js library to create a Stripe Checkout
Session. It should accept a "priceId" in the request body and create a checkout
session in "payment" mode with that price. Set the success_url to
"http://localhost:3000/success" and the cancel_url to "http://localhost:3000/cancel."
Use the Stripe test secret key from an environment variable called STRIPE_SECRET_KEY.
Add the cors middleware so the frontend can call it. Include comments explaining
what each part does.
```

✅ **Expected result:** A server file (like `server.js`) with a single API endpoint that creates Stripe Checkout sessions. You'll see clear comments explaining the flow.

### Step 3 — Connect the Buttons to Stripe Checkout

Make the pricing page buttons actually do something.

```
Update the pricing page so that when a user clicks "Get Started" or "Go Pro," it
sends a fetch POST request to the /create-checkout-session backend endpoint with the
correct Stripe Price ID. After getting the session URL back from the server, redirect
the user to the Stripe Checkout page. For now, use placeholder Price IDs like
"price_starter_123" and "price_pro_456" — I'll replace these with real ones from my
Stripe Dashboard later. The "Contact Us" button on the Enterprise tier should open a
mailto link instead. Add a loading spinner to the buttons while the request is in
progress.
```

> 💡 **Tip:** To get real Price IDs, go to your Stripe Dashboard → Products → create a product → copy the Price ID (it starts with `price_`). In test mode, you can use Stripe's test card number `4242 4242 4242 4242` with any future expiration date and any three-digit CVC.

✅ **Expected result:** Clicking a pricing button shows a spinner, then redirects you to Stripe's hosted checkout page.

### Step 4 — Build the Success Page

After payment, celebrate! 🎉

```
Create a success page at /success that shows a large green checkmark animation, the
headline "Payment Successful!" and a message that says "Thank you for your purchase.
You'll receive a confirmation email shortly." Add a "Go to Dashboard" button that
links to the home page. Include confetti animation on the page for a fun touch.
Also create a cancel page at /cancel that shows a neutral message: "Payment
cancelled. No worries — you can try again whenever you're ready." with a "Back to
Pricing" button.
```

✅ **Expected result:** Two new pages — a cheerful success page with animation and a friendly cancellation page, both with navigation buttons.

### Step 5 — Add Stripe Webhook Handling

This is how your server finds out the payment actually went through.

```
Add a POST endpoint at /webhook to the Express server that handles Stripe webhook
events. Use the Stripe library's constructEvent method to verify the webhook
signature (using a STRIPE_WEBHOOK_SECRET environment variable). Handle the
"checkout.session.completed" event — when it fires, log the customer's email and the
amount paid to the console. For now, just console.log the details. Add a comment
that says "TODO: Save this to your database and send a confirmation email." Include
error handling that returns a 400 status if the webhook signature verification fails.
```

> 💡 **Tip:** To test webhooks locally, use the [Stripe CLI](https://stripe.com/docs/stripe-cli): run `stripe listen --forward-to localhost:3000/webhook` in your terminal. It gives you a temporary webhook secret to use.

✅ **Expected result:** A webhook endpoint that verifies Stripe signatures and logs payment details. You'll see customer info in your terminal when a test payment completes.

### Step 6 — Test the Full Flow

Pull it all together and make sure it works end to end.

```
Add a README file to this project with clear setup instructions. Include:
1. How to install dependencies (npm install)
2. How to set the environment variables STRIPE_SECRET_KEY and STRIPE_WEBHOOK_SECRET
3. How to start the server
4. How to test the checkout flow using Stripe's test card (4242 4242 4242 4242)
5. How to test webhooks using the Stripe CLI
Also add a .env.example file with placeholder values for the two environment
variables so other developers know what's needed.
```

✅ **Expected result:** A README with clear setup instructions and a `.env.example` file. Anyone (including future-you) can get the project running.

---

## Recipe 4: Simple Chatbot for Your Business

**What you're building:** A chatbot that lives on your website and answers customer questions. It can either use pre-set responses (for common questions like "What are your hours?") or connect to OpenAI's API for smarter, more flexible answers.

**Why it matters:** A chatbot works 24/7, never calls in sick, and can handle the same "What's your return policy?" question a thousand times without getting grumpy. It's one of the highest-impact things you can add to a small business website.

- ⏱ **Time estimate:** 35–50 minutes
- 📊 **Difficulty:** Intermediate
- 🛠 **Tools:** [Bolt](https://bolt.new) or [Lovable](https://lovable.dev) + [OpenAI API](https://platform.openai.com)

> ⚠️ **Before you start:** If you want the smart (AI-powered) version, sign up at [platform.openai.com](https://platform.openai.com) and create an API key. You'll get some free credits to start. The pre-set-response version works without any API key.

### Step 1 — Build the Chat Interface

First, create the visual chat window.

```
Build a chat widget that sits in the bottom-right corner of the page as a floating
button. When clicked, it expands into a chat window. The chat window should have:
- A header bar with the title "Chat with us 💬" and a close (X) button
- A message area that scrolls when there are many messages
- An input field at the bottom with a placeholder "Type your message..." and a send
  button
Style user messages as blue bubbles aligned to the right and bot messages as gray
bubbles aligned to the left. Show a small avatar icon next to bot messages. Add a
typing indicator (three animated dots) that appears briefly before the bot responds.
The chat should start with an automatic greeting: "Hi there! 👋 How can I help you
today?"
```

✅ **Expected result:** A floating chat bubble in the corner that opens into a polished chat window with message bubbles and a typing indicator.

### Step 2 — Add Pre-Set Responses

Start simple — handle the most common questions without any AI.

```
Add a pre-set response system to the chatbot. When the user sends a message, check
it against these keyword-based rules (case-insensitive):
- If the message contains "hours" or "open" → Reply: "We're open Monday–Friday,
  9 AM to 6 PM Eastern. Closed on weekends and holidays!"
- If the message contains "price" or "cost" or "pricing" → Reply: "Our plans start
  at $9/month. Check out our pricing page at example.com/pricing for all the
  details!"
- If the message contains "refund" or "return" or "cancel" → Reply: "We offer a
  full refund within 30 days, no questions asked. Just email support@example.com
  and we'll take care of it."
- If the message contains "contact" or "email" or "phone" → Reply: "You can reach
  us at support@example.com or call (555) 123-4567 during business hours."
- For anything else → Reply: "Great question! I'm not sure about that one. Would
  you like me to connect you with a human? Email us at support@example.com."
Add a short delay (1-2 seconds) before showing the bot's reply so it feels natural.
```

✅ **Expected result:** The chatbot responds correctly to keywords like "hours," "pricing," or "refund" and has a friendly fallback for anything it doesn't recognize.

### Step 3 — Upgrade to OpenAI-Powered Responses

Now let's make the bot actually smart.

```
Replace the keyword-based responses with OpenAI API integration. Create a backend
endpoint at /api/chat that accepts a POST request with the user's message. Use the
OpenAI chat completions API (gpt-3.5-turbo model) with this system prompt:

"You are a friendly and helpful customer support assistant for a SaaS company called
BrightTools. You help customers with questions about pricing (plans start at $9/mo),
business hours (Mon-Fri 9-6 ET), refund policy (30-day full refund), and general
product questions. Keep responses short (2-3 sentences max), friendly, and helpful.
If you don't know something, suggest they email support@brighttools.com."

Use the OPENAI_API_KEY from an environment variable. Send the last 10 messages as
conversation history so the bot has context. Handle errors gracefully — if the API
call fails, show the message "I'm having trouble connecting right now. Please try
again or email support@brighttools.com."
```

✅ **Expected result:** The chatbot now gives intelligent, conversational responses powered by OpenAI, with context awareness across messages.

### Step 4 — Add Quick-Reply Buttons

Help users get started without typing.

```
When the chat first opens, show 4 quick-reply buttons below the greeting message.
The buttons should say: "Pricing Info," "Business Hours," "Refund Policy," and
"Talk to a Human." When a user clicks one of these buttons, it should send that
text as a message in the chat (just like they typed it). The buttons should disappear
after one is clicked. Style the buttons as rounded pill shapes with a light border,
and they should appear in a horizontal scrollable row if they don't all fit on
screen.
```

✅ **Expected result:** Four clickable quick-reply buttons appear at the start of the conversation. Clicking one sends it as a message and the buttons vanish.

### Step 5 — Add Sound and Notification Badges

Make sure people notice when the bot replies.

```
Add a subtle notification sound that plays when the bot sends a new message (use a
short, pleasant chime — you can use a base64-encoded audio or a small mp3 file).
Also add a red notification badge on the floating chat button that shows the number
of unread messages when the chat window is closed. The badge should disappear when
the user opens the chat window. Make the sound optional — add a small mute/unmute
icon in the chat header.
```

✅ **Expected result:** A soft chime plays on new messages, a red badge shows unread count on the closed chat button, and there's a mute toggle.

### Step 6 — Generate an Embed Code

Let people drop this chatbot onto any website.

```
Create an embed instructions page at /embed that shows users how to add the chatbot
to their own website. Display a code snippet in a copyable code block that looks like
this:

<script src="https://yoursite.com/chatbot-widget.js"></script>

Add a "Copy to Clipboard" button next to the code block. Below it, include simple
instructions:
1. Copy the code snippet above
2. Paste it just before the </body> tag on your website
3. The chat widget will appear automatically in the bottom-right corner

Also refactor the chatbot into a single standalone JavaScript file called
chatbot-widget.js that can be loaded on any page and creates the chat widget
automatically.
```

✅ **Expected result:** An embed page with a copyable code snippet and a self-contained widget file that works on any website.

---

## Recipe 5: Chrome Extension

**What you're building:** A Chrome browser extension — a little tool that adds a button to your browser and can interact with the web pages you visit. In this recipe, you'll build a "reading mode" extension that cleans up cluttered articles so they're easy to read.

**Why it matters:** Chrome extensions are a surprisingly accessible way to build something useful. Over 100,000 extensions exist in the Chrome Web Store, and many successful micro-businesses started as simple extensions. The skills here also apply to Edge, Brave, and other Chromium-based browsers.

- ⏱ **Time estimate:** 40–55 minutes
- 📊 **Difficulty:** Intermediate
- 🛠 **Tools:** [Cursor](https://cursor.sh) or [Windsurf](https://codeium.com/windsurf)

### Step 1 — Create the Manifest and Project Structure

Every Chrome extension starts with a `manifest.json` — think of it as the extension's ID card.

```
Create a Chrome Extension project with a manifest.json file (Manifest V3). The
extension should be called "CleanRead" with the description "Remove clutter and
read articles in a clean, focused view." Set up the following structure:
- manifest.json with permissions for "activeTab" and "scripting"
- A popup HTML file (popup.html) with a simple UI
- A popup JavaScript file (popup.js)
- A content script file (content.js) that will run on web pages
- A folder called "icons" with a placeholder note about where to add 16x16, 48x48,
  and 128x128 icon images
Include comments in the manifest.json explaining what each field does.
```

✅ **Expected result:** A clean project folder with `manifest.json`, popup files, a content script, and an icons folder. The manifest has helpful comments explaining each field.

### Step 2 — Build the Popup UI

The popup is the little window that appears when someone clicks your extension icon.

```
Design the popup.html to be 320px wide and nicely styled. It should contain:
- The extension name "CleanRead" as a heading with a small book emoji 📖
- A brief tagline: "Read without distractions"
- A large toggle button that says "Enable Clean Mode" — when toggled on, it should
  change to "Disable Clean Mode" and change color from blue to green
- A section with 3 small checkboxes for options:
  1. "Hide images" (unchecked by default)
  2. "Dark mode" (unchecked by default)
  3. "Large text" (checked by default)
- A small footer that says "v1.0 — Made with ❤️"
Style everything with a clean, modern look. Save checkbox states to Chrome's
storage API so they persist between popup opens. Wire up the toggle button in
popup.js to send a message to the content script.
```

✅ **Expected result:** A polished popup with a toggle button and three options. Checking/unchecking options is saved even after closing the popup.

### Step 3 — Build the Content Script

This is the magic part — the code that actually transforms web pages.

```
Create the content.js content script that listens for a message from the popup. When
it receives the "enable" message, it should:
1. Find the main article content on the page (look for <article>, <main>, or the
   element with the most <p> tags)
2. Hide everything else on the page (sidebars, ads, navigation, footers)
3. Restyle the article content with: centered layout (max-width 700px), comfortable
   line-height (1.8), readable font (Georgia or system serif), generous padding, and
   a clean white background
4. If the "Hide images" option is on, hide all images inside the article
5. If "Dark mode" is on, switch to a dark background with light text
6. If "Large text" is on, increase the font size to 20px (default is 18px)
When it receives the "disable" message, restore the page to its original state.
```

✅ **Expected result:** Clicking the toggle in the popup transforms a cluttered webpage into a clean, readable view. Toggling off brings the page back to normal.

### Step 4 — Add a Keyboard Shortcut

Power users love keyboard shortcuts.

```
Add a keyboard shortcut to toggle CleanRead on and off. Register Ctrl+Shift+R
(or Command+Shift+R on Mac) as the shortcut in the manifest.json commands section.
Create a background service worker (background.js) that listens for the keyboard
command and sends the toggle message to the active tab. Update the manifest to
include the background service worker. Also show the keyboard shortcut as a hint
in the popup UI, styled as a small gray badge like "Ctrl+Shift+R" near the toggle
button.
```

✅ **Expected result:** Pressing Ctrl+Shift+R toggles clean reading mode without opening the popup. The shortcut is displayed in the popup UI.

### Step 5 — Add a Page Stats Feature

Give readers useful info about what they're reading.

```
When CleanRead mode is enabled, add a small floating bar at the top of the cleaned
article that shows:
- Estimated reading time (calculate based on word count, assuming 200 words per
  minute)
- Total word count
- A small progress bar that fills up as the user scrolls through the article
Style the floating bar with a subtle background that stays fixed at the top of the
viewport. It should not cover any article content (add appropriate top padding).
When CleanRead is disabled, remove this bar along with everything else.
```

✅ **Expected result:** A slim info bar at the top showing reading time, word count, and a scroll progress indicator.

### Step 6 — Test and Package for Distribution

Get it ready for the real world.

```
Create a README.md for the CleanRead extension project with:
1. A project description and screenshot placeholder
2. Installation instructions for loading the extension locally:
   - Open Chrome and go to chrome://extensions
   - Enable "Developer mode" in the top right
   - Click "Load unpacked" and select the project folder
   - The extension icon will appear in your browser toolbar
3. Usage instructions explaining the toggle, options, and keyboard shortcut
4. A section called "Publishing to Chrome Web Store" with a brief outline of the
   steps (create a developer account for $5, zip the extension folder, upload it)
Also add a .gitignore file that excludes node_modules, .DS_Store, and any
local environment files.
```

✅ **Expected result:** A complete README with install, usage, and publishing instructions, plus a `.gitignore`. Your extension is ready to share!

---

## Recipe 6: Mobile-Responsive Web App (PWA)

**What you're building:** A Progressive Web App — a website that feels and behaves like a native phone app. Users can install it on their home screen, use it offline, and get an app-like experience with smooth navigation, all without going through the App Store.

**Why it matters:** Building a native iOS or Android app is expensive and complicated. A PWA gives you 90% of the benefits — home screen icon, full-screen mode, offline support — with a fraction of the effort. And it works on every device with a browser.

- ⏱ **Time estimate:** 40–55 minutes
- 📊 **Difficulty:** Intermediate
- 🛠 **Tools:** [Bolt](https://bolt.new) or [Lovable](https://lovable.dev)

### Step 1 — Create the App Shell with Navigation

The "app shell" is the skeleton of your app — the parts that stay constant while content changes.

```
Build a Progressive Web App called "FitTrack" — a simple fitness tracking app. Create
the app shell with:
- A bottom navigation bar with 4 tabs (like a phone app): Home (house icon), Workouts
  (dumbbell icon), Progress (chart icon), and Profile (person icon)
- Each tab should highlight when active and show a different page/view
- A top header bar that shows the current page name and a small FitTrack logo
- Use smooth transitions when switching between tabs (slide or fade animations)
- Design it mobile-first: the bottom nav should be thumb-friendly with large tap
  targets (at least 48px tall). On desktop, optionally move the nav to a sidebar.
Make the overall color scheme energetic — use a bright green or teal as the primary
color.
```

✅ **Expected result:** A mobile-first app with four tappable tabs at the bottom, smooth page transitions, and a header bar. It should feel like using a phone app.

### Step 2 — Build the Home Screen

Give users a useful landing page when they open the app.

```
Create the Home tab content with:
- A greeting at the top: "Welcome back, Alex! 💪" with today's date
- A circular progress ring in the center showing daily step count: "6,482 / 10,000
  steps" with the ring 65% filled in green
- Below the ring, three small stat cards in a row: "Calories: 1,840," "Water:
  5 glasses," "Sleep: 7.2 hrs"
- A "Today's Workout" card below that shows: "Upper Body Strength — 45 min" with
  a "Start Workout" button
- A "Weekly Streak" section at the bottom showing 7 circles for each day of the
  week (Mon–Sun), with completed days filled in green and today pulsing with an
  animation
Use sample/hardcoded data for now. The layout should scroll naturally on small
screens.
```

✅ **Expected result:** A content-rich home screen with a progress ring, stat cards, workout card, and weekly streak — all looking great on a phone-sized screen.

### Step 3 — Add the PWA Manifest and Service Worker

This is what makes it *installable* — the jump from "website" to "app."

```
Add the PWA configuration files:
1. Create a manifest.json (web app manifest) with:
   - name: "FitTrack"
   - short_name: "FitTrack"
   - start_url: "/"
   - display: "standalone" (this hides the browser UI)
   - background_color and theme_color set to your teal/green
   - Icons at 192x192 and 512x512 sizes (use placeholder colored squares for now)
2. Create a service worker (sw.js) that:
   - Caches the app shell files on install (HTML, CSS, JS, icons)
   - Serves cached files when offline (cache-first strategy)
   - Shows a friendly "You're offline" message if a requested page isn't cached
3. Register the service worker in the main app
4. Add the manifest link and theme-color meta tag to the HTML head
Include a comment in the service worker explaining the caching strategy in plain
English.
```

> 💡 **Tip:** After adding these files, open Chrome DevTools (F12) → Application tab → Manifest. You should see your app info. Under "Service Workers," you'll see yours registered. This is how you know it's working!

✅ **Expected result:** Your app can now be "installed" — Chrome will show an install prompt in the address bar. It also works offline for cached pages.

### Step 4 — Make It Fully Responsive

Make sure it looks great on every screen size, from tiny phones to big monitors.

```
Update the entire FitTrack app to be fully responsive:
- On phones (under 640px): single-column layout, bottom tab navigation, large touch
  targets, the progress ring should be about 60% of screen width
- On tablets (640px–1024px): two-column grid for stat cards and workout cards, bottom
  navigation stays, progress ring is a reasonable size
- On desktop (over 1024px): move navigation to a left sidebar, use a three-column
  layout for the stat cards, show more data per screen since there is more room
Use CSS media queries or responsive utility classes. Test that nothing overflows or
looks broken at any width. Make sure all text is readable (minimum 16px on mobile)
and all buttons are easy to tap (minimum 44px tap targets).
```

✅ **Expected result:** Resize your browser window from narrow to wide and the app gracefully adapts its layout at each breakpoint. No horizontal scrolling, no broken layouts.

### Step 5 — Add the Workouts Page

Fill out the second tab with useful content.

```
Create the Workouts tab with:
- A search/filter bar at the top with buttons to filter by category: "All,"
  "Strength," "Cardio," "Flexibility," "HIIT"
- A list of 6 workout cards, each showing: workout name, duration, difficulty tag
  (Easy/Medium/Hard with color coding), a small icon, and a short description. Use
  these workouts:
  1. "Morning Run" — 30 min — Easy (green tag) — Cardio
  2. "Upper Body Blast" — 45 min — Hard (red tag) — Strength
  3. "Yoga Flow" — 25 min — Easy (green tag) — Flexibility
  4. "HIIT Circuit" — 20 min — Hard (red tag) — HIIT
  5. "Core Crusher" — 15 min — Medium (yellow tag) — Strength
  6. "Stretching Routine" — 20 min — Easy (green tag) — Flexibility
- When a filter button is clicked, only show matching workouts with a smooth
  animation. The "All" button shows everything.
- Tapping a workout card should expand it to show the full description and a
  "Start Workout" button.
```

✅ **Expected result:** A filterable workout list with animated transitions and expandable cards. Each filter button works correctly.

### Step 6 — Add an Install Prompt

Nudge users to install the app on their home screen.

```
Add a custom "Install App" banner that appears at the bottom of the screen (above
the tab bar) on the user's second visit to the app. The banner should say "Add
FitTrack to your home screen for the best experience" with an "Install" button and
a small "X" to dismiss it. When the user clicks "Install," trigger the browser's
native PWA install prompt using the beforeinstallprompt event. After the user
installs (or dismisses), hide the banner and save that choice to localStorage so
it doesn't appear again. Also add an "Install App" option in the Profile tab as a
fallback for users who dismissed the banner.
```

> 💡 **Tip:** To test the install prompt, open your app in Chrome, click the three-dot menu, and look for "Install FitTrack." If you see it, your PWA is configured correctly! On mobile, you'll get a proper "Add to Home Screen" option.

✅ **Expected result:** A polite install banner appears on the second visit, triggers the real browser install flow, and never shows again once the user responds. Your PWA is complete!

---

## What's Next?

You've now got six real projects under your belt — from landing pages to payment systems to browser extensions. Here's the thing: **every complex app is just a combination of patterns like these.**

A SaaS product? That's Recipe 1 (landing page) + Recipe 3 (payments) + Recipe 2 (dashboard).
A customer-facing tool? That's Recipe 6 (PWA) + Recipe 4 (chatbot).

Mix, match, and remix. You've got the recipes — now go cook something amazing. 🚀
