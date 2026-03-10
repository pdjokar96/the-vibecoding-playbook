# 📋 Recipe: Waitlist App with Admin Dashboard

> Build a full waitlist system with a Supabase database, an admin panel to view and manage signups, and CSV export — all without writing code by hand.

---

## At a Glance

| Detail | Info |
|---|---|
| **Difficulty** | 🟡 Beginner–Intermediate |
| **Time Estimate** | 2–3 hours |
| **Tools Needed** | AI coding assistant (Cursor, GitHub Copilot, or Bolt), a free Supabase account, a free Vercel account |
| **Prerequisites** | A computer with a browser. It helps (but isn't required) to have done the [Landing Page recipe](./landing-page.md) first. |
| **What You'll Build** | A waitlist signup form, a Supabase database to store emails, a password-protected admin dashboard, and a CSV export button |

---

## Before You Start

1. **Sign up for Supabase** — Go to [supabase.com](https://supabase.com) and create a free account.
2. **Create a new Supabase project** — Click "New Project," give it a name (like "my-waitlist"), set a database password (save it somewhere safe!), and pick the region closest to you.
3. **Grab your keys** — In your Supabase dashboard, go to **Settings → API**. You'll need two things:
   - **Project URL** (looks like `https://abc123.supabase.co`)
   - **Anon public key** (a long string starting with `eyJ...`)
4. **Open your AI coding tool** and get ready to build!

---

## Step 1: Set Up the Database Table

First, let's create the database table where emails will be stored. In your Supabase dashboard, go to the **SQL Editor** and run this prompt through your AI assistant:

> **Prompt:**
>
> Write a SQL statement I can run in Supabase to create a waitlist table with these columns:
>
> - `id` — auto-generated unique ID (use UUID)
> - `email` — the person's email address (required, unique — no duplicates)
> - `name` — optional full name
> - `referral_source` — optional field for how they heard about us
> - `created_at` — automatically set to the current date and time
> - `status` — either "pending," "approved," or "rejected" (default to "pending")
>
> Also set up Row Level Security (RLS) so that:
> - Anyone can INSERT a new row (for the public signup form)
> - Only authenticated users can SELECT, UPDATE, or DELETE rows (for the admin dashboard)

Take the SQL your AI gives you and paste it into the Supabase SQL Editor. Click **Run**. You should see a success message.

✅ **What to check:** Go to **Table Editor** in Supabase. You should see your `waitlist` table with all the columns listed.

---

## Step 2: Scaffold the Project

> **Prompt:**
>
> Create a new Next.js project with TypeScript, Tailwind CSS, and the Supabase JavaScript client. Set up the project structure like this:
>
> - `app/page.tsx` — public waitlist signup page
> - `app/admin/page.tsx` — admin dashboard (protected)
> - `app/admin/login/page.tsx` — admin login page
> - `app/api/waitlist/route.ts` — API endpoint for form submissions
> - `app/api/waitlist/export/route.ts` — API endpoint for CSV export
> - `lib/supabase.ts` — Supabase client setup
> - `components/SignupForm.tsx` — the email signup form
> - `components/AdminTable.tsx` — table showing all signups
> - `components/ExportButton.tsx` — button to download CSV
>
> Install the Supabase client library (`@supabase/supabase-js`). Create a `.env.local` file with placeholders for `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_ANON_KEY`.

✅ **What to check:** Your project folder should have all those files. Fill in your `.env.local` with the Supabase URL and anon key you grabbed earlier.

---

## Step 3: Build the Supabase Client

> **Prompt:**
>
> Set up the Supabase client in `lib/supabase.ts`. Create two versions:
>
> 1. A public client that uses the anon key (for the signup form)
> 2. A note in the comments about how to create an admin/service-role client for server-side operations
>
> Read the URL and key from environment variables `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_ANON_KEY`.

---

## Step 4: Create the Signup Form

> **Prompt:**
>
> Build the SignupForm component with these features:
>
> - Email input field (required)
> - Name input field (optional)
> - "How did you hear about us?" dropdown with options: Twitter, LinkedIn, Friend, Blog Post, Other (optional)
> - A big, friendly "Join the Waitlist" submit button
> - When submitted, send the data to the `/api/waitlist` endpoint
> - Show a loading spinner while submitting
> - Show a success state: "You're on the list! 🎉 We'll be in touch soon."
> - Show an error state if something goes wrong (like a duplicate email: "Looks like you're already signed up!")
> - Style it beautifully with Tailwind — centered on the page, clean card design, subtle shadows
>
> Also build the API route at `app/api/waitlist/route.ts` that:
> - Receives the form data
> - Validates the email format
> - Inserts it into the Supabase `waitlist` table
> - Returns success or an appropriate error message

✅ **What to check:** Run `npm run dev` and try signing up with a test email. Then check your Supabase Table Editor — you should see the entry appear!

---

## Step 5: Build the Public Signup Page

> **Prompt:**
>
> Update `app/page.tsx` to be a beautiful public waitlist page. Include:
>
> - A hero section with my product name **[YOUR PRODUCT NAME]** and tagline **[YOUR TAGLINE]**
> - A brief description of what the product does (2–3 sentences)
> - The SignupForm component prominently displayed
> - A live counter showing how many people have signed up (fetch the count from Supabase)
> - A simple footer with contact info
>
> Make it look professional and trustworthy — this is the first thing potential users will see.

---

## Step 6: Build the Admin Login Page

> **Prompt:**
>
> Create a simple admin login page at `app/admin/login/page.tsx`:
>
> - Email and password input fields
> - A "Sign In" button
> - Use Supabase Auth to handle the login
> - On successful login, redirect to `/admin`
> - On failure, show an error message like "Invalid email or password"
> - Style it cleanly — centered card on a neutral background
>
> For now, I'll create the admin user manually in Supabase. Add a comment explaining how to do that:
> Go to Supabase Dashboard → Authentication → Users → "Add User" and create an account with your email and a strong password.

✅ **What to check:** Create an admin user in your Supabase dashboard first. Then try logging in on the login page. You should be redirected to `/admin`.

---

## Step 7: Build the Admin Dashboard

> **Prompt:**
>
> Build the admin dashboard at `app/admin/page.tsx` with these features:
>
> - **Protected route** — if the user isn't logged in, redirect them to `/admin/login`
> - **Stats bar at the top** showing:
>   - Total signups
>   - Signups today
>   - Signups this week
>   - Signups this month
> - **Search and filter bar** — search by email or name, filter by status (all, pending, approved, rejected)
> - **Data table** showing all waitlist entries with columns: Email, Name, Source, Date, Status
> - **Status management** — clicking on a status should let me change it (pending → approved or rejected)
> - **Pagination** — show 25 entries per page with next/previous buttons
> - **Logout button** in the top right
>
> Use the AdminTable component for the table. Fetch data from Supabase. Style everything with Tailwind — make it look like a proper admin dashboard with a clean, professional feel.

✅ **What to check:** Log in and you should see your test signup(s) in the table. Try changing a status, searching, and filtering.

---

## Step 8: Add CSV Export

> **Prompt:**
>
> Build the CSV export feature:
>
> 1. Create the ExportButton component — a button that says "Export to CSV" with a download icon
> 2. Create the API route at `app/api/waitlist/export/route.ts` that:
>    - Checks that the user is authenticated (admin only)
>    - Fetches all waitlist entries from Supabase
>    - Converts them to CSV format (columns: Email, Name, Referral Source, Status, Signup Date)
>    - Returns the CSV as a downloadable file
> 3. Add the ExportButton to the admin dashboard, next to the search bar
>
> When clicked, the browser should download a file called `waitlist-export-[today's date].csv`.

✅ **What to check:** Click the export button. A CSV file should download. Open it in Excel or Google Sheets — you should see all your waitlist entries.

---

## Step 9: Add Email Notifications (Optional but Nice)

> **Prompt:**
>
> Add an optional email notification feature. When someone signs up for the waitlist:
>
> 1. Send them a confirmation email saying "You're on the waitlist!" with a friendly message
> 2. Send me (the admin) a notification email saying "New waitlist signup: [email]"
>
> Use the Resend API for sending emails. The API key should be in an environment variable called `RESEND_API_KEY`.
>
> Make this feature toggle-able — if the RESEND_API_KEY isn't set, the signup should still work fine, just without email notifications. Add a comment explaining this.

---

## Step 10: Polish and Deploy

> **Prompt:**
>
> Do a final polish pass:
>
> 1. Add proper error handling everywhere — no crashes, just friendly error messages
> 2. Add loading states to the admin table and stats
> 3. Make sure the admin dashboard is fully responsive on mobile
> 4. Add meta tags for SEO on the public signup page
> 5. Add a favicon
>
> Then help me deploy to Vercel:
> - List the environment variables I need to add in the Vercel dashboard
> - Give me the git commands to push and deploy
> - Remind me to create the admin user in Supabase if I haven't already

### Deployment Commands

```bash
git init
git add .
git commit -m "Waitlist app with admin dashboard"
gh repo create my-waitlist-app --public --push
```

Then in Vercel:
1. Import the GitHub repo
2. Add environment variables:
   - `NEXT_PUBLIC_SUPABASE_URL`
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY`
   - `RESEND_API_KEY` (if using email notifications)
3. Deploy!

---

## 🎉 You Did It!

You now have a fully functional waitlist system with:
- ✅ A beautiful public signup page
- ✅ Email data stored safely in Supabase
- ✅ A password-protected admin dashboard
- ✅ Search, filter, and status management
- ✅ CSV export for your spreadsheet needs
- ✅ Optional email notifications

### What to Do Next

- **Share your waitlist page** everywhere your potential users hang out
- **Check your admin dashboard** daily to watch signups grow
- **Export your CSV** and import it into your email marketing tool when you're ready to launch
- **Try the [Landing Page recipe](./landing-page.md)** if you want a fancier public-facing page
- **Upgrade to the [Customer Support Chatbot recipe](./chatbot.md)** to add a chat widget to your waitlist page

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "No rows returned" in admin | Make sure you've signed up at least one test email through the public form |
| Login not working | Double-check that you created an admin user in Supabase Dashboard → Authentication → Users |
| Duplicate email error | That's actually working correctly! The table is set to reject duplicate emails |
| CSV is empty | Make sure you're logged in as admin — the export endpoint requires authentication |
| Supabase connection error | Check your `.env.local` values. Make sure there are no extra spaces. Restart the dev server after changing environment variables. |
| RLS policy errors | Go back to Step 1 and make sure the Row Level Security policies were applied correctly in the SQL Editor |
