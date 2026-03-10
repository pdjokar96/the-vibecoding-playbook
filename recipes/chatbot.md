# 🤖 Recipe: Customer Support Chatbot

> Build a friendly chatbot that answers your customers' most common questions — and embed it right on your website. Optionally connect it to OpenAI for smarter, more flexible answers.

---

## At a Glance

| Detail | Info |
|---|---|
| **Difficulty** | 🟡 Beginner–Intermediate |
| **Time Estimate** | 2–3 hours |
| **Tools Needed** | AI coding assistant (Cursor, GitHub Copilot, or Bolt), a free Vercel account, and (optionally) an OpenAI API key |
| **Prerequisites** | A list of 10–20 frequently asked questions and their answers. If you don't have them yet, we'll help you come up with them! |
| **What You'll Build** | A chat widget that lives in the corner of your website, answers FAQs instantly, and (optionally) uses AI to handle questions you didn't anticipate |

---

## Before You Start

1. **Gather your FAQs** — Write down the questions your customers (or potential customers) ask most often. Things like:
   - "What does your product do?"
   - "How much does it cost?"
   - "Do you offer a free trial?"
   - "How do I cancel my subscription?"
   - "How do I contact support?"

   Aim for 10–20 questions. Don't have any yet? No problem — your AI assistant can help you brainstorm them in Step 3.

2. **Open your AI coding tool** and let's go!

---

## Step 1: Scaffold the Project

> **Prompt:**
>
> Create a new Next.js project with TypeScript and Tailwind CSS for a customer support chatbot. Set up the following structure:
>
> - `app/page.tsx` — a demo page where we can test the chatbot
> - `app/api/chat/route.ts` — API endpoint that handles chat messages
> - `components/ChatWidget.tsx` — the floating chat bubble and chat window
> - `components/ChatMessage.tsx` — individual chat message component (supports both user and bot messages)
> - `lib/faq-data.ts` — the FAQ knowledge base
> - `lib/chat-engine.ts` — the logic that matches questions to answers
>
> Install any dependencies needed. Set up placeholder content in each file.

---

## Step 2: Build the Chat Widget UI

> **Prompt:**
>
> Build the ChatWidget component — a floating chat bubble that opens a chat window. Here's what I need:
>
> - **Chat bubble:** A round button fixed to the bottom-right corner of the page with a chat icon (💬 emoji is fine). It should have a subtle bounce animation to attract attention.
> - **Chat window:** When clicked, a chat window opens above the bubble. It should be about 380px wide and 500px tall.
> - **Chat window layout:**
>   - Header bar with my product name, a "Powered by [Product Name]" note, and an X button to close
>   - Message area showing the conversation (scrollable, newest messages at the bottom)
>   - Input area with a text field and a Send button
> - **Welcome message:** When the chat opens, show a friendly welcome message from the bot: "Hi there! 👋 I'm here to help. Ask me anything about [Product Name], or pick a common question below."
> - **Quick reply buttons:** Below the welcome message, show 3–4 clickable buttons with common questions (like "What do you do?" "How much does it cost?" "How do I get started?")
> - **Typing indicator:** When the bot is "thinking," show an animated typing indicator (three bouncing dots)
> - **Smooth animations:** The chat window should slide up smoothly when opened and slide down when closed
>
> Use the ChatMessage component for each message. Style everything with Tailwind — make it look professional and friendly.

✅ **What to check:** Run `npm run dev` and you should see a chat bubble in the bottom-right corner. Click it — a beautiful chat window should slide open with a welcome message and quick reply buttons.

---

## Step 3: Create Your FAQ Knowledge Base

> **Prompt:**
>
> Set up the FAQ knowledge base in `lib/faq-data.ts`. Create a data structure that stores question-and-answer pairs. Here are my FAQs:
>
> 1. **Q:** What does [Product Name] do?
>    **A:** [Your answer]
>
> 2. **Q:** How much does it cost?
>    **A:** [Your answer]
>
> 3. **Q:** Do you offer a free trial?
>    **A:** [Your answer]
>
> 4. **Q:** How do I sign up?
>    **A:** [Your answer]
>
> 5. **Q:** How do I contact support?
>    **A:** [Your answer]
>
> [Add as many as you want — aim for 10–20]
>
> For each FAQ, also include a list of keywords and alternative phrasings so the chatbot can match questions even if they're worded differently. For example, "How much does it cost?" should also match "pricing," "price," "how much," "subscription," "plans," etc.
>
> If I don't have enough FAQs, generate realistic ones for a typical SaaS product and I'll customize them later.

💡 **Tip:** Don't stress about covering every possible question right now. Start with the basics, launch it, and then add more FAQs over time as you see what people actually ask.

---

## Step 4: Build the Chat Engine (FAQ Matching)

> **Prompt:**
>
> Build the chat engine in `lib/chat-engine.ts` that matches user messages to FAQ answers. Here's how it should work:
>
> 1. **Keyword matching** — Compare the user's message against the keywords for each FAQ. Use case-insensitive matching and ignore common words like "the," "a," "is," "how," etc.
> 2. **Fuzzy matching** — Handle slight misspellings and partial matches. For example, "pricng" should still match "pricing."
> 3. **Confidence scoring** — Rate each potential match from 0 to 1. If the best match scores above 0.5, return that answer. If it scores between 0.3 and 0.5, return the answer but add "I'm not 100% sure this is what you're asking, but..."
> 4. **Fallback message** — If no match scores above 0.3, respond with: "I'm not sure I can help with that one! You can email us at [YOUR EMAIL] and a human will get back to you within 24 hours. 😊"
> 5. **Quick replies** — After each answer, suggest 2–3 related questions the user might want to ask next (as clickable buttons)
>
> Also create the API route at `app/api/chat/route.ts` that:
> - Receives the user's message
> - Runs it through the chat engine
> - Returns the bot's response and suggested quick replies

✅ **What to check:** Go to your chat widget and try asking a question. Try exact matches ("How much does it cost?"), casual variations ("what's the price?"), and questions not in your FAQ list. The chatbot should handle all three scenarios.

---

## Step 5: Add Conversation Memory

> **Prompt:**
>
> Upgrade the chatbot to remember the conversation context:
>
> 1. **Conversation history** — Keep track of all messages in the current session (both user and bot messages). Store it in the component state (no need for a database).
> 2. **Context awareness** — If the user says "tell me more about that," the bot should know what "that" refers to (the topic of the previous answer).
> 3. **Greeting detection** — If the user says "hi," "hello," "hey," etc., respond with a friendly greeting instead of trying to match it to an FAQ.
> 4. **Thank you detection** — If the user says "thanks," "thank you," etc., respond with "You're welcome! Let me know if you have any other questions. 😊"
> 5. **Clear history** — Add a small "Clear conversation" button in the chat header that resets the chat to the welcome state.

---

## Step 6: Connect to OpenAI (Optional — For Smarter Answers)

This step is optional! Your chatbot already works great with just FAQ matching. But if you want it to handle *any* question — even ones not in your FAQ list — you can connect it to OpenAI.

> **Prompt:**
>
> Upgrade the chat engine to optionally use the OpenAI API for questions the FAQ matching can't answer. Here's how it should work:
>
> 1. **First, try FAQ matching** — If there's a high-confidence match (above 0.5), use the FAQ answer. This is faster and cheaper.
> 2. **If no FAQ match, use OpenAI** — Send the question to the OpenAI API (model: `gpt-4o-mini` for cost efficiency) with a system prompt that includes:
>    - My product name and description
>    - All my FAQs as context
>    - Instructions to be helpful, friendly, and concise
>    - Instructions to say "I'd recommend contacting our team at [EMAIL]" if the question is about something the AI can't reliably answer (like account-specific issues)
> 3. **Environment variable** — Use `OPENAI_API_KEY` from environment variables. If the key isn't set, just use the FAQ fallback message instead (no crash).
> 4. **Rate limiting** — Add basic rate limiting (max 10 AI-powered responses per session) to prevent abuse and control costs
> 5. **Streaming** — Stream the OpenAI response so the answer appears word by word (feels more natural)
>
> Update the API route and chat engine accordingly. Add `OPENAI_API_KEY` to `.env.local`.

✅ **What to check:** Try asking the chatbot something NOT in your FAQ list. If your OpenAI key is set, it should give a smart, contextual answer. If the key isn't set, it should gracefully fall back to the "contact us" message.

---

## Step 7: Make It Embeddable

This is the magic step — making your chatbot a simple widget that can be dropped into *any* website with a single line of code.

> **Prompt:**
>
> Make the chatbot embeddable on any website:
>
> 1. Create a `public/embed.js` script that:
>    - Creates an iframe pointing to my chatbot page
>    - Adds the floating chat bubble and handles opening/closing the chat window
>    - Works on any website — WordPress, Shopify, Squarespace, plain HTML, anything
>    - Is configurable (primary color, position, welcome message) via data attributes
> 2. Create a clean embed page at `app/embed/page.tsx` that renders just the chat interface (no demo page wrapper)
> 3. Generate the embed code snippet that website owners would copy-paste:
>
> ```html
> <script src="https://your-chatbot.vercel.app/embed.js" data-color="#4F46E5" data-position="bottom-right"></script>
> ```
>
> 4. On the demo page (`app/page.tsx`), show the embed code in a copyable code block so I can easily grab it

---

## Step 8: Add Analytics (Know What People Are Asking)

> **Prompt:**
>
> Add simple analytics to track what people are asking the chatbot:
>
> 1. Create an API route at `app/api/analytics/route.ts` that logs each chat interaction
> 2. Log: the user's question, the bot's response type (FAQ match, AI response, or fallback), the confidence score, and a timestamp
> 3. Store the logs in a simple JSON file on the server (or in Supabase if I have it set up from another recipe)
> 4. Create a simple analytics page at `app/analytics/page.tsx` that shows:
>    - Total conversations today / this week / all time
>    - Most frequently asked questions (top 10)
>    - Questions that got the "fallback" response (these are FAQs you should add!)
>    - A simple bar chart showing conversations over time
> 5. Protect the analytics page with a simple password (environment variable `ADMIN_PASSWORD`)

💡 **Tip:** The "fallback" questions are gold! They tell you exactly what FAQs to add next. Check this page regularly and keep growing your knowledge base.

---

## Step 9: Polish and Deploy

> **Prompt:**
>
> Final polish pass on the chatbot:
>
> 1. Add a smooth typing animation for bot messages (characters appearing one by one for FAQ answers)
> 2. Add a subtle sound effect option when a new message arrives (disabled by default, togglable in settings)
> 3. Add a "Was this helpful?" thumbs up/down after each bot answer
> 4. Make sure the widget works well on mobile — full-screen chat on small screens
> 5. Add a "Powered by [Your Product]" link in the chat footer (good for marketing if others use your chatbot!)
> 6. Test the embed script on a plain HTML page to make sure it works
>
> Then deploy to Vercel:
> - List all environment variables needed
> - Give me the deployment commands

### Deployment

```bash
git init
git add .
git commit -m "Customer support chatbot"
gh repo create my-chatbot --public --push
```

In Vercel:
1. Import the repository
2. Add environment variables:
   - `OPENAI_API_KEY` (optional — only if using the AI-powered responses)
   - `ADMIN_PASSWORD` (for the analytics page)
3. Deploy!

After deploying, grab your embed code from the demo page and add it to your website.

---

## 🎉 You Did It!

You just built a customer support chatbot that:
- ✅ Answers FAQs instantly — no waiting for a human
- ✅ Handles casual, natural language questions
- ✅ Optionally uses AI for questions you didn't anticipate
- ✅ Can be embedded on any website with one line of code
- ✅ Tracks what people are asking so you can keep improving

### What to Do Next

- **Embed it on your website** — copy the embed code and paste it into your site
- **Monitor the analytics page** — see what people are asking and add more FAQs
- **Customize the personality** — tweak the welcome message, tone, and quick replies to match your brand
- **Combine it with the [Waitlist recipe](./saas-waitlist.md)** — add a "Join our waitlist" option in the chatbot
- **Level up** — add a way for users to escalate to a human (email notification when the bot can't help)

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Chat window doesn't open | Check the browser console for JavaScript errors. Make sure the ChatWidget component is imported and rendered. |
| Bot always says "I can't help with that" | Your keywords might be too narrow. Add more alternative phrasings to your FAQ data. Try the OpenAI integration for better matching. |
| OpenAI responses are slow | That's normal — AI responses take 1–3 seconds. The streaming feature (Step 6) makes it feel faster. You can also try `gpt-4o-mini` which is faster and cheaper. |
| Embed script doesn't work on my site | Make sure you're using the full URL to your deployed chatbot (not `localhost`). Check that your site doesn't have Content Security Policy headers blocking external scripts. |
| Rate limit hit | The 10-response-per-session limit is there to protect your wallet. Adjust the number in the code if needed, or just rely on FAQ matching (it's free!). |
| Analytics page is blank | Make sure you've set the `ADMIN_PASSWORD` environment variable and you're entering the correct password. |
