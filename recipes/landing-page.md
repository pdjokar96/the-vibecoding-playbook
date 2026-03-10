# 🚀 Recipe: SaaS Landing Page with Email Waitlist

> Turn your idea into a real, live landing page — complete with a waitlist — in under two hours. No coding experience required.

---

## At a Glance

| Detail | Info |
|---|---|
| **Difficulty** | 🟢 Beginner |
| **Time Estimate** | 1–2 hours |
| **Tools Needed** | AI coding assistant (Cursor, GitHub Copilot, or Bolt), a free Vercel account, a free Resend or Mailchimp account |
| **Prerequisites** | A computer with a browser, a rough idea of what your product does |
| **What You'll Build** | A polished single-page website with a hero section, features grid, pricing, testimonials, email signup, and footer — deployed live on the internet |

---

## Before You Start

1. **Sign up for Vercel** — Go to [vercel.com](https://vercel.com) and create a free account (you can sign in with GitHub).
2. **Sign up for Resend** — Go to [resend.com](https://resend.com) and create a free account. Grab your API key from the dashboard. *(Alternative: use [Mailchimp](https://mailchimp.com) if you prefer — we'll cover both.)*
3. **Open your AI coding tool** — Launch Cursor, Bolt, or whichever AI assistant you're using.
4. **Jot down your product details** — You'll need: your product name, a one-sentence tagline, 3–4 key features, and (optionally) pricing tiers and testimonial quotes.

---

## Step 1: Scaffold the Project

Open your AI assistant and paste this prompt:

> **Prompt:**
>
> Create a new Next.js project for a SaaS landing page. Use the App Router, TypeScript, and Tailwind CSS. Set up the project structure with these components:
>
> - `app/page.tsx` — the main landing page
> - `components/Hero.tsx`
> - `components/Features.tsx`
> - `components/Pricing.tsx`
> - `components/Testimonials.tsx`
> - `components/EmailSignup.tsx`
> - `components/Footer.tsx`
>
> Don't add any content yet — just create the files with placeholder text so I can see the structure. Make sure `app/page.tsx` imports and renders all the components in order.

✅ **What to check:** You should now have a project folder with all those files. Run `npm run dev` (or let your AI tool do it) and you should see a basic page with placeholder text.

---

## Step 2: Build the Hero Section

> **Prompt:**
>
> Update the Hero component to create a stunning hero section for my SaaS product. Here are the details:
>
> - **Product Name:** [YOUR PRODUCT NAME]
> - **Tagline:** [YOUR ONE-SENTENCE TAGLINE]
> - **Description:** [A short paragraph about what it does and who it's for]
>
> Design guidelines:
> - Use a gradient background (something modern — like indigo to purple, or blue to teal)
> - Big, bold headline with the product name
> - Tagline underneath in a slightly smaller font
> - A clear call-to-action button that says "Join the Waitlist" and scrolls down to the email signup section
> - Make it look polished and professional, like a Y Combinator startup landing page
> - Fully responsive (looks great on phones too)

✅ **What to check:** Refresh your page. You should see a beautiful, eye-catching hero section. Try resizing your browser window to make sure it looks good on mobile too.

---

## Step 3: Create the Features Grid

> **Prompt:**
>
> Update the Features component to show a grid of features for my product. Here are my features:
>
> 1. **[Feature 1 Name]** — [One sentence explaining it]
> 2. **[Feature 2 Name]** — [One sentence explaining it]
> 3. **[Feature 3 Name]** — [One sentence explaining it]
> 4. **[Feature 4 Name]** — [One sentence explaining it]
>
> Design guidelines:
> - Use a clean 2x2 grid on desktop, stacking to a single column on mobile
> - Each feature card should have an emoji or simple icon, a bold title, and a short description
> - Add a section heading above the grid like "Why you'll love [Product Name]"
> - Use subtle card shadows or borders to make each feature stand out
> - Keep the overall style consistent with the hero section

✅ **What to check:** You should see four neat cards arranged in a grid. On mobile, they should stack vertically.

---

## Step 4: Add the Pricing Section

> **Prompt:**
>
> Update the Pricing component to show a pricing section with three tiers:
>
> 1. **Free** — $0/month — [List 3–4 features included]
> 2. **Pro** — $[PRICE]/month — [List 5–6 features included]
> 3. **Enterprise** — Custom pricing — [List 7–8 features included]
>
> Design guidelines:
> - Show three pricing cards side by side on desktop, stacking on mobile
> - Highlight the "Pro" tier as the recommended/popular option (add a "Most Popular" badge and a subtle border or background highlight)
> - Each card should list the tier name, price, feature list with checkmarks, and a call-to-action button
> - The Free and Enterprise buttons should say "Get Started" and "Contact Us"
> - The Pro button should say "Join the Waitlist" and link to the email signup section
> - Keep the visual style consistent with the rest of the page

💡 **Tip:** Don't have pricing figured out yet? That's totally fine! Use placeholder prices — you can always change them later. The important thing is getting the page live.

---

## Step 5: Add Testimonials

> **Prompt:**
>
> Update the Testimonials component to show social proof. Create a testimonials section with these quotes:
>
> 1. **"[Quote 1]"** — [Name], [Title/Company]
> 2. **"[Quote 2]"** — [Name], [Title/Company]
> 3. **"[Quote 3]"** — [Name], [Title/Company]
>
> Design guidelines:
> - Display testimonials in a horizontal row on desktop, stacking on mobile
> - Each testimonial should show the quote in italics, the person's name in bold, and their title underneath
> - Add quotation mark decorations or a subtle card style
> - Include a section heading like "What people are saying" or "Loved by early users"
> - If I don't have real testimonials yet, generate realistic-sounding placeholder quotes from fictional founders and product managers who would use a tool like [YOUR PRODUCT NAME]

💡 **Tip:** No real testimonials yet? Use the AI-generated placeholders for now. Once you get real feedback from early users, swap them in!

---

## Step 6: Build the Email Signup Form

This is the most important part — it's how people join your waitlist!

### Option A: Using Resend

> **Prompt:**
>
> Update the EmailSignup component to create a waitlist signup section. When someone enters their email and clicks "Join the Waitlist," it should:
>
> 1. Save their email using the Resend API (I'll provide the API key as an environment variable called `RESEND_API_KEY`)
> 2. Send them a welcome email confirming they've joined the waitlist
> 3. Show a success message like "You're on the list! 🎉 Check your inbox."
> 4. Handle errors gracefully (show a friendly error message if something goes wrong)
>
> Also create an API route at `app/api/waitlist/route.ts` that handles the form submission server-side.
>
> Design guidelines:
> - Big, attention-grabbing section heading like "Be the first to know"
> - Subheading like "Join [X] others on the waitlist" (use a placeholder number for now)
> - Email input field with a "Join the Waitlist" button next to it on desktop, stacking on mobile
> - Add a small note under the form like "No spam, ever. Unsubscribe anytime."
> - The section should have a background color that makes it stand out from the rest of the page

### Option B: Using Mailchimp

> **Prompt:**
>
> Update the EmailSignup component to create a waitlist signup section that connects to Mailchimp. When someone enters their email and clicks "Join the Waitlist," it should:
>
> 1. Add their email to my Mailchimp audience list using the Mailchimp API
> 2. My Mailchimp API key will be in an environment variable called `MAILCHIMP_API_KEY`, and my audience/list ID will be in `MAILCHIMP_LIST_ID`
> 3. Show a success message like "You're on the list! 🎉"
> 4. Handle errors gracefully
>
> Create an API route at `app/api/waitlist/route.ts` for the server-side logic.
>
> Use the same design guidelines: attention-grabbing heading, email input with button, "no spam" note, standout background color.

✅ **What to check:** Try submitting an email. You should see the success message. Check your Resend dashboard (or Mailchimp audience) to confirm the email was received.

---

## Step 7: Create the Footer

> **Prompt:**
>
> Update the Footer component to create a simple, clean footer with:
>
> - The product name and a one-line description
> - Links to: Twitter/X, GitHub (if applicable), and an email address for contact
> - A "Built with ❤️ by [Your Name]" note
> - Copyright notice with the current year
> - Keep it minimal and elegant — dark background with light text works well

---

## Step 8: Add the Environment Variables

> **Prompt:**
>
> Create a `.env.local` file with placeholder environment variables for the waitlist API. Add comments explaining what each one is for:
>
> ```
> # Resend API Key (get yours at https://resend.com)
> RESEND_API_KEY=your_resend_api_key_here
>
> # Or, if using Mailchimp:
> # MAILCHIMP_API_KEY=your_mailchimp_api_key_here
> # MAILCHIMP_LIST_ID=your_list_id_here
> ```
>
> Also make sure `.env.local` is in the `.gitignore` file so we don't accidentally share our secrets.

✅ **What to check:** Replace the placeholder with your real API key. Test the email signup again to make sure it still works.

---

## Step 9: Polish and Final Touches

> **Prompt:**
>
> Do a final polish pass on the entire landing page:
>
> 1. Add smooth scroll behavior so clicking "Join the Waitlist" buttons scrolls smoothly to the signup section
> 2. Add a simple fade-in animation to each section as you scroll down the page (use CSS animations or Framer Motion — keep it subtle)
> 3. Add proper meta tags for SEO: title, description, and Open Graph tags so the page looks good when shared on social media
> 4. Make sure the page has no accessibility issues — proper heading hierarchy, alt text, and form labels
> 5. Double-check mobile responsiveness on all sections

---

## Step 10: Deploy to Vercel

> **Prompt:**
>
> Help me deploy this Next.js project to Vercel. Walk me through the steps:
>
> 1. Initialize a git repository if there isn't one already
> 2. Create a `.gitignore` that excludes `node_modules`, `.env.local`, and `.next`
> 3. Push the code to a GitHub repository
> 4. Connect the GitHub repo to Vercel
> 5. Add my environment variables (RESEND_API_KEY) in the Vercel dashboard
> 6. Deploy!
>
> Give me the exact terminal commands I need to run and tell me where to click in the Vercel dashboard.

Here's the quick version of the terminal commands you'll need:

```bash
# Initialize git and push to GitHub
git init
git add .
git commit -m "Initial landing page"
gh repo create my-landing-page --public --push

# Or if you prefer to create the repo on GitHub.com manually:
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
git push -u origin main
```

Then in the Vercel dashboard:
1. Click **"Add New Project"**
2. Import your GitHub repository
3. Click **"Environment Variables"** and add your `RESEND_API_KEY`
4. Click **"Deploy"**

✅ **What to check:** Vercel will give you a URL like `your-project.vercel.app`. Visit it! Your landing page is now live on the internet. Share the link with friends and start collecting waitlist signups!

---

## 🎉 You Did It!

You just built and deployed a professional SaaS landing page — with a working email waitlist — and you didn't write a single line of code by hand. That's the power of vibe coding.

### What to Do Next

- **Share your link** on Twitter/X, LinkedIn, or in communities where your target audience hangs out
- **Iterate on the copy** — the words matter more than the design. Keep tweaking your headline and description
- **Check your Resend/Mailchimp dashboard** regularly to see signups rolling in
- **Try the [Waitlist App with Admin Dashboard](./saas-waitlist.md) recipe** to build a more advanced system with a Supabase backend

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "Module not found" errors | Ask your AI: *"I'm getting a module not found error for [module name]. How do I fix it?"* |
| Email signup not working | Double-check your API key in `.env.local`. Make sure there are no extra spaces. Restart the dev server. |
| Page looks weird on mobile | Ask your AI: *"The [section name] doesn't look right on mobile. Can you fix the responsive layout?"* |
| Vercel deploy fails | Check the build logs in the Vercel dashboard. Copy the error and paste it to your AI assistant. |
| Emails going to spam | This is normal at first. With Resend, set up a custom domain to improve deliverability. |
