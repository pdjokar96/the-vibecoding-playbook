# 📋 Product Requirements Document (PRD) Template

Use this template before building any new app or major feature. Fill it out in plain English — no technical jargon needed. The more specific you are, the better your AI assistant can help you build it.

---

## 1. Project Overview

**App Name**: [Your app's name]

**One-Line Description**: [Describe your app in one sentence — what it does and who it's for]

**Example**: *"ClientFlow is a client management tool for freelance designers to track projects, send invoices, and communicate with clients in one place."*

---

## 2. Problem Statement

**What problem does this solve?**

[Describe the pain point your target user faces. Be specific — don't say "it's hard to manage clients." Say "freelance designers currently juggle 3-4 separate tools (email, spreadsheets, invoicing apps) to manage client relationships, wasting 5+ hours per week."]

**Example**: *"Freelance designers currently use Google Sheets for project tracking, Gmail for client communication, and Stripe's invoice tool for billing. Information is scattered, things fall through the cracks, and it takes too long to find a client's project history."*

---

## 3. Target User

**Who is this for?**

[Describe your ideal user. Be as specific as possible.]

- **Role/Job**: [e.g., Freelance graphic designer]
- **Experience Level**: [e.g., 2-10 years of freelancing experience]
- **Current Tools**: [e.g., Google Sheets, Gmail, Stripe, Notion]
- **Pain Points**: [e.g., Information scattered across tools, manual invoice tracking, no project overview]
- **Tech Comfort**: [e.g., Comfortable with web apps, uses Canva and Figma daily]

**Example**: *"Solo freelance designers with 5-20 active clients who are comfortable with web apps but don't want to learn complex project management software like Monday.com or Asana."*

---

## 4. Core Features (MVP)

List only the features you need for launch — the minimum set that makes the app useful. You can always add more later.

| # | Feature | Description | Priority |
|---|---------|-------------|----------|
| 1 | [Feature name] | [What it does in 1-2 sentences] | Must Have |
| 2 | [Feature name] | [What it does in 1-2 sentences] | Must Have |
| 3 | [Feature name] | [What it does in 1-2 sentences] | Must Have |
| 4 | [Feature name] | [What it does in 1-2 sentences] | Nice to Have |
| 5 | [Feature name] | [What it does in 1-2 sentences] | Nice to Have |

**Example**:

| # | Feature | Description | Priority |
|---|---------|-------------|----------|
| 1 | Client profiles | Add clients with name, email, company, and notes | Must Have |
| 2 | Project tracking | Create projects linked to clients with status (Active/Completed/On Hold) | Must Have |
| 3 | Simple invoicing | Generate and send invoices with line items and due dates | Must Have |
| 4 | Dashboard | Overview showing active projects, pending invoices, and recent activity | Must Have |
| 5 | File sharing | Upload and share files within a project | Nice to Have |

---

## 5. User Flows

Describe the main paths a user takes through your app. Think of it as a story: "The user does X, then sees Y, then does Z."

### Flow 1: [Name of flow]

**Example — "New Client Onboarding":**

1. User clicks "Add Client" button on the dashboard
2. A form appears with fields: Name, Email, Company, Phone, Notes
3. User fills in the details and clicks "Save"
4. App creates the client profile and shows it
5. User can immediately create a new project for this client

### Flow 2: [Name of flow]

[Describe another key flow]

### Flow 3: [Name of flow]

[Describe another key flow]

---

## 6. Design Preferences

**Visual Style**: [e.g., Clean and minimal, Colorful and playful, Professional and corporate]

**Color Preferences**: [e.g., Blues and whites, Dark mode, Warm earth tones]

**Inspiration**: [List 1-3 apps or websites whose design you like and why]

**Example**: *"Clean and minimal, like Linear or Notion. Light mode with a blue accent color. Should feel professional but not stuffy."*

---

## 7. Tech Preferences (Optional)

If you have preferences for tools or technologies, list them here. If not, your AI assistant will choose sensible defaults.

- **Frontend**: [e.g., Next.js, React, or "whatever you recommend"]
- **Backend/Database**: [e.g., Supabase, Firebase, or "whatever you recommend"]
- **Authentication**: [e.g., Email/password, Google login, Magic links]
- **Hosting**: [e.g., Vercel, Railway, or "whatever's easiest"]
- **Payments**: [e.g., Stripe, Lemon Squeezy, or "not needed yet"]

---

## 8. Success Criteria

How will you know this app is successful? Define 2-3 measurable goals.

| Metric | Target | Timeframe |
|--------|--------|-----------|
| [Metric] | [Number] | [When] |
| [Metric] | [Number] | [When] |
| [Metric] | [Number] | [When] |

**Example**:

| Metric | Target | Timeframe |
|--------|--------|-----------|
| Active users | 50 | 3 months after launch |
| Paying subscribers | 10 | 3 months after launch |
| Client satisfaction | 4+ stars average | 6 months after launch |

---

## 9. What's NOT in Scope

Just as important as what you're building is what you're *not* building (yet). This prevents scope creep.

**Example**:
- ❌ Mobile app (web only for now)
- ❌ Team collaboration features (solo freelancers only)
- ❌ Time tracking (may add later)
- ❌ Contract generation (may add later)
- ❌ Integration with accounting software

---

## 10. Future Ideas (Parking Lot)

Features you'd love to have eventually, but not for the MVP. Writing them down here means you won't forget them — and you won't try to cram them into version 1.

- [ ] [Future feature 1]
- [ ] [Future feature 2]
- [ ] [Future feature 3]
- [ ] [Future feature 4]

---

## How to Use This PRD

1. **Fill it out** in plain English — this is for you and your AI, not for investors
2. **Share the whole thing** with your AI assistant at the start of your project
3. **Reference specific sections** when building individual features
4. **Update it** as you learn from user feedback
5. **Keep it simple** — a 1-page PRD that you actually use beats a 20-page document that collects dust

> 💡 **Pro tip**: Paste this entire filled-out PRD into your AI assistant and say: *"Here's my PRD. Let's start building. Which feature should we tackle first, and what's the plan?"*
