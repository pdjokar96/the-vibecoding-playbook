# Chapter 16: After Launch — Now What? 📊

Your app is live. You shared the link. Maybe a few people clicked it. Maybe a lot of people clicked it. Either way, you're probably wondering: *"Now what?"*

Launching is a milestone, but it's not the finish line. The real work — and the real fun — starts now. This chapter is about turning your launched app into something that grows, improves, and maybe even earns you money.

---

## Analytics: Knowing If People Use Your App

You wouldn't open a store and never check if customers walk in, right? Analytics tell you what's happening with your app: who's visiting, what they're clicking, and where they're dropping off.

### Why Analytics Matter

Without analytics, you're flying blind. You might spend a week building a fancy new feature that nobody uses, while ignoring a simple bug that's driving people away. Analytics help you make decisions based on **reality**, not guesses.

### Simple Analytics Options

You don't need anything complicated. Here are three beginner-friendly options:

#### 1. Vercel Analytics (If You Deployed on Vercel)
- **Cost**: Free tier available
- **Setup**: One click in your Vercel dashboard
- **What you get**: Page views, unique visitors, top pages, performance metrics
- **Best for**: Simple websites and apps on Vercel

#### 2. Plausible
- **Cost**: Starting at $9/month (or free if self-hosted)
- **Setup**: Add one line of code to your HTML
- **What you get**: Clean, privacy-friendly analytics — visitors, pages, referrers, countries
- **Best for**: People who want simple, ethical analytics without cookie banners
- **How to add it**:
```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

#### 3. PostHog
- **Cost**: Free up to 1 million events/month
- **Setup**: Add their JavaScript snippet
- **What you get**: Analytics, session recordings, feature flags, A/B testing
- **Best for**: Apps where you want to watch how users actually use features

> 💡 **Which should you pick?** If you're on Vercel, start with Vercel Analytics. If you want more detail, add PostHog. If you care about privacy, choose Plausible.

### What Metrics Actually Matter?

It's easy to get lost in numbers. Here are the metrics that actually help you make decisions:

| Metric | What It Tells You | Why It Matters |
|--------|-------------------|----------------|
| **Unique Visitors** | How many different people visit | Is your app getting discovered? |
| **Signups** | How many people create accounts | Are visitors interested enough to commit? |
| **Activation Rate** | % of signups who complete a key action | Is your app delivering value quickly? |
| **Retention** | % of users who come back | Are people finding ongoing value? |
| **Feature Usage** | Which features get clicked | What should you build more of? |

**The one metric that matters most for solopreneurs: Retention.** Getting people to visit once is marketing. Getting them to come back is product quality.

### What's an "Activation" Event?

This is the moment a new user first gets value from your app. It's different for every app:

- **Todo app**: Creating their first task
- **Booking tool**: Making their first appointment
- **Content platform**: Publishing their first post
- **Invoice tool**: Sending their first invoice

Ask your AI: *"I'm building a [type of app]. What would be a good activation event to track?"*

---

## Collecting User Feedback

Analytics tell you *what* people do. Feedback tells you *why*. Both are essential.

### In-App Feedback Widgets

The easiest way to get feedback is to put a feedback button right inside your app.

**Simple approaches:**
- A "Feedback" button in the corner that opens a text box
- A tiny form that pops up after someone completes a key action
- A "Was this helpful? 👍 👎" prompt on important pages

**Ask your AI**: *"Add a simple feedback widget to my app. It should have a button that opens a form with a text area and a submit button. Store feedback in my database."*

**Dedicated tools** (if you want something fancier):
- **Canny** — users can suggest and vote on features (free tier available)
- **Tally** — beautiful free forms you can embed anywhere
- **Google Forms** — free, familiar, gets the job done

### Social Media and Communities

Don't just wait for feedback to come to you. Go where your users hang out:

- **Reddit**: Find subreddits related to your app's niche. Share your app (following community rules!) and ask for honest feedback
- **X/Twitter**: Post about your building journey. People love following solopreneurs who build in public
- **Product Hunt**: Great for a "launch day" burst of traffic and feedback
- **Indie Hackers**: A community specifically for people building small software businesses
- **Relevant Discord servers**: Many niches have active Discord communities

### Simple Survey Tools

For deeper feedback, send a short survey to your users:

- **Tally** (free) — clean, modern surveys
- **Typeform** (free tier) — conversational surveys that feel friendly
- **Google Forms** (free) — simple and reliable

**Keep surveys short**: 3-5 questions maximum. Here are great questions to ask:

1. *"What's the main thing you use [app name] for?"*
2. *"What's the most frustrating thing about [app name]?"*
3. *"If you could add one feature, what would it be?"*
4. *"How would you feel if you could no longer use [app name]?"* (Very disappointed / Somewhat disappointed / Not disappointed)
5. *"How did you hear about us?"*

> 💡 Question #4 is the famous "Sean Ellis test." If 40%+ say "very disappointed," you have product-market fit. That's the gold standard.

---

## Iterating with AI After Launch

This is where vibe coding really shines. You can respond to user feedback and ship improvements *fast* — sometimes within hours.

### Prioritizing User Feedback

Not all feedback is equal. Here's a simple framework for deciding what to work on:

```
┌─────────────────────────────────────────────┐
│           IMPACT vs. EFFORT Matrix           │
├──────────────────┬──────────────────────────┤
│                  │                          │
│  HIGH IMPACT     │  HIGH IMPACT             │
│  LOW EFFORT      │  HIGH EFFORT             │
│                  │                          │
│  → DO FIRST! 🏃  │  → Plan carefully 📋     │
│                  │                          │
├──────────────────┼──────────────────────────┤
│                  │                          │
│  LOW IMPACT      │  LOW IMPACT              │
│  LOW EFFORT      │  HIGH EFFORT             │
│                  │                          │
│  → Nice to have  │  → Don't bother ❌       │
│                  │                          │
└──────────────────┴──────────────────────────┘
```

### Bug Fixes vs. New Features

**Rule of thumb**: Fix bugs before adding features. A broken app with 10 features is worse than a working app with 3 features.

Priority order:
1. 🔴 **Crashes and data loss** — fix immediately
2. 🟠 **Broken features** — fix within a day or two
3. 🟡 **Annoying quirks** — fix this week
4. 🟢 **Feature requests** — plan and build thoughtfully

### The "One Improvement Per Day" Habit

Here's a habit that will transform your app over time: make **one small improvement every day**.

It doesn't have to be big. It could be:
- Fixing a typo
- Improving an error message
- Making a button more visible
- Adding a loading spinner
- Speeding up a slow page

One improvement per day = 30 improvements per month = 365 improvements per year.

**Your daily prompt to AI:**
> *"Here's my app's current state: [describe or paste context]. The next small improvement I want to make is [improvement]. Please help me implement it."*

Commit after each improvement. Push to GitHub. Auto-deploy handles the rest. Your app gets better every single day.

---

## Cost Management

One of the beautiful things about vibe coding is that you can build and launch for almost nothing. But as your app grows, costs can creep up. Let's be smart about this.

### Free Tier Limits for Common Services

| Service | Free Tier | When You'll Hit the Limit |
|---------|-----------|--------------------------|
| **Vercel** | 100 GB bandwidth | ~50,000-100,000 page views/month |
| **Railway** | $5 credit/month | Small app with light traffic |
| **Supabase** | 500 MB database, 50K users | After storing significant data |
| **Netlify** | 100 GB bandwidth, 300 build min | Similar to Vercel |
| **Cloudflare Pages** | Unlimited bandwidth | Very generous — hard to exceed |
| **PostHog** | 1M events/month | After significant user activity |
| **GitHub** | Unlimited public repos | Probably never |

### When You'll Need to Start Paying

Here's the honest truth about scaling costs:

- **0-100 users**: Almost everything stays free. Don't worry about costs.
- **100-1,000 users**: You might hit one or two free tier limits. Budget $10-30/month.
- **1,000-10,000 users**: You'll likely need paid plans. Budget $50-150/month.
- **10,000+ users**: Time to think seriously about infrastructure. But you should also have revenue by now!

### Budget Planning for Solopreneurs

Here's a realistic monthly budget at different stages:

**Stage 1: Just Launched (0-100 users)**
| Item | Monthly Cost |
|------|-------------|
| Domain name | ~$1 (annual cost divided by 12) |
| Hosting | $0 (free tier) |
| Database | $0 (free tier) |
| AI assistant | $20 (ChatGPT Plus or similar) |
| **Total** | **~$21/month** |

**Stage 2: Growing (100-1,000 users)**
| Item | Monthly Cost |
|------|-------------|
| Domain name | ~$1 |
| Hosting (Vercel Pro or Railway) | $20 |
| Database (Supabase Pro) | $25 |
| AI assistant | $20 |
| Email service (Resend, Mailgun) | $0-10 |
| **Total** | **~$66-76/month** |

**Stage 3: Scaling (1,000-10,000 users)**
| Item | Monthly Cost |
|------|-------------|
| Domain name | ~$1 |
| Hosting | $40-100 |
| Database | $50-100 |
| AI assistant | $20 |
| Email service | $20-30 |
| Analytics | $0-20 |
| Error monitoring | $0-30 |
| **Total** | **~$131-301/month** |

> 💡 **Key insight**: If you have 1,000+ active users, you should be generating enough revenue to cover these costs. If not, your pricing or monetization strategy needs work (see Chapter 18).

---

## Growing Your User Base

You've built it. It works. Now how do you get people to actually use it?

### The Solopreneur's Growth Playbook

#### 1. Build in Public 🏗️

Share your journey on social media. People love watching things being built:
- Post screenshots of new features
- Share your daily improvements
- Talk about challenges and how you solved them
- Show your analytics (transparently)

This builds an audience that's invested in your success *before* your product is polished.

#### 2. Solve Problems in Communities 🤝

Don't just promote your app — help people first:
- Answer questions in relevant subreddits, forums, and Discord servers
- When your app genuinely solves someone's problem, mention it naturally
- Write helpful blog posts or tutorials related to your app's domain

#### 3. Get Featured 📰

- **Product Hunt**: Plan a launch day — prepare assets, descriptions, and rally early supporters
- **Indie Hackers**: Share your story and what you learned
- **Hacker News (Show HN)**: For tech-savvy audiences
- **Niche blogs and newsletters**: Reach out to writers who cover your app's area

#### 4. Make Sharing Easy 🔗

Build sharing into your app:
- "Share your results" buttons
- Referral systems (even simple ones)
- Make your app's output shareable (images, links, reports)

#### 5. Talk to Users Directly 💬

This is the most underrated growth strategy:
- Personally email or message your first 100 users
- Ask them what they think
- Ask them if they know anyone else who'd find it useful
- People are surprisingly willing to help when you ask genuinely

### Growth Takes Time

A realistic timeline:
- **Week 1-2**: Your friends and family try it (10-50 users)
- **Month 1**: People from your social media / communities try it (50-200 users)
- **Month 2-3**: Word of mouth starts — if your app is genuinely useful (200-500 users)
- **Month 3-6**: Organic growth compounds if retention is good (500-2,000 users)

Don't compare yourself to viral apps with millions of users. Most successful solo businesses grow slowly and steadily. **Consistency beats virality.**

---

## Your Post-Launch Daily Routine

Here's a simple daily routine that keeps your app improving:

| Time | Activity | Duration |
|------|----------|----------|
| Morning | Check analytics — any spikes or drops? | 5 min |
| Morning | Read any new feedback or messages | 10 min |
| Anytime | Make one improvement to your app | 30-60 min |
| Anytime | Share something about your journey online | 10 min |
| Evening | Commit your changes and push to deploy | 5 min |

**Total time: About 1-1.5 hours per day.** That's manageable even with a full-time job.

---

## What's Next?

You're now running a live app and improving it based on real user data. You're doing what professional product teams do — just faster and leaner.

In the next chapter, we'll look at the patterns that successful vibe coders use over and over again — and the anti-patterns that trip beginners up.

---

> **Key Takeaway**: Launch is the starting line, not the finish line. Add analytics from day one, collect feedback constantly, and make one small improvement every day. Growth is a marathon, not a sprint.

[← Previous: Deploying Your App](../15-deploying/README.md) | [Next: Patterns That Work →](../17-patterns/README.md)
