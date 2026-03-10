# 📐 Project Rules Starter Template

This is a starter rules file for your AI coding assistant. Copy this file into your project as `.cursorrules` (for Cursor) or `CLAUDE.md` (for Claude) or similar, and customize it for your specific project.

**What this does**: It gives your AI assistant persistent context about your project so you don't have to re-explain everything in every conversation. Think of it as a cheat sheet your AI reads before helping you.

---

## How to Use

1. Copy the content below into a file in your project root
2. Replace all `[bracketed sections]` with your project details
3. Update it as your project evolves
4. Your AI assistant will automatically read this file and follow these guidelines

---

## Template — Copy Everything Below This Line

```markdown
# Project Rules

## Project Overview

**Name**: [Your App Name]
**Description**: [One-paragraph description of what your app does and who it's for]
**Stage**: [MVP / Beta / Production]

## Tech Stack

- **Framework**: [e.g., Next.js 14 (App Router)]
- **Language**: [e.g., TypeScript]
- **Styling**: [e.g., Tailwind CSS]
- **UI Components**: [e.g., shadcn/ui]
- **Database**: [e.g., Supabase (PostgreSQL)]
- **Authentication**: [e.g., Supabase Auth]
- **Hosting**: [e.g., Vercel]
- **Payments**: [e.g., Stripe (if applicable)]

## Project Structure

```
[Paste your project's folder structure here. You can generate it with:]
[Run: tree -I node_modules -I .git --dirsfirst]

Example:
src/
├── app/                  # Next.js App Router pages
│   ├── (auth)/           # Auth-related pages (login, signup)
│   ├── (dashboard)/      # Protected dashboard pages
│   ├── api/              # API routes
│   └── layout.tsx        # Root layout
├── components/           # Reusable UI components
│   ├── ui/               # Base UI components (shadcn)
│   └── [feature]/        # Feature-specific components
├── lib/                  # Utility functions and configurations
│   ├── supabase.ts       # Supabase client
│   └── utils.ts          # Helper functions
└── types/                # TypeScript type definitions
```

## Code Style & Conventions

### General Rules
- Write clean, readable code with descriptive variable names
- Use TypeScript for type safety
- Keep components small and focused (under 150 lines ideally)
- Use server components by default, client components only when needed

### Naming Conventions
- **Files**: kebab-case (e.g., `user-profile.tsx`)
- **Components**: PascalCase (e.g., `UserProfile`)
- **Functions**: camelCase (e.g., `getUserData`)
- **Constants**: SCREAMING_SNAKE_CASE (e.g., `MAX_RETRY_COUNT`)
- **Database tables**: snake_case (e.g., `user_profiles`)

### Component Patterns
- Use functional components with hooks
- Co-locate component-specific types in the same file
- Extract reusable logic into custom hooks in `hooks/` directory
- Use [shadcn/ui or your UI library] for base components, customize as needed

### Data Fetching
- [Describe your data fetching pattern, e.g.:]
- Use Server Components for initial data loading
- Use Supabase client for real-time subscriptions
- Handle loading and error states in every data-fetching component

### Error Handling
- Always show user-friendly error messages (never raw errors)
- Log errors for debugging but don't expose internals to users
- Use try/catch in async functions
- Display toast notifications for action results (success and error)

## Database Schema

[Describe your main tables and their relationships]

Example:
- **users**: Managed by Supabase Auth
- **profiles**: id, user_id (FK), display_name, avatar_url, created_at
- **projects**: id, user_id (FK), title, description, status, created_at, updated_at
- **tasks**: id, project_id (FK), title, completed, position, created_at

Relationships:
- Each user has one profile
- Each user has many projects
- Each project has many tasks

## Authentication & Authorization

- [Describe your auth setup]
- Using Supabase Auth with email/password
- Protected routes check for session in middleware
- Row Level Security (RLS) enabled on all tables
- Users can only CRUD their own data

## Environment Variables

[List your environment variable NAMES — never put actual values here!]

```
# Supabase
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=

# Stripe (if applicable)
STRIPE_SECRET_KEY=
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=
STRIPE_WEBHOOK_SECRET=

# Other
[Any other env vars your app uses]
```

## Current Status & Known Issues

[Update this section as your project evolves]

### What's Working
- [Feature 1] ✅
- [Feature 2] ✅
- [Feature 3] ✅

### In Progress
- [Feature being built]

### Known Issues
- [Bug or issue to be aware of]
- [Technical debt item]

### Upcoming Features
- [Next feature to build]
- [Feature after that]

## AI Assistant Guidelines

When helping with this project:

1. **Follow existing patterns**: Look at how similar features are already implemented before creating new ones
2. **Keep it simple**: Choose the simplest approach that solves the problem
3. **Don't over-engineer**: We're building an MVP — avoid premature optimization
4. **Explain your changes**: When you modify something, briefly explain why
5. **Handle edge cases**: Always consider what happens with empty data, errors, and unauthorized access
6. **Mobile-first**: Ensure all UI changes work on mobile screens
7. **Preserve existing functionality**: Don't break working features when adding new ones
8. **Use existing utilities**: Check `lib/` and `components/` before creating duplicate functionality
```

---

## Tips for Maintaining Your Rules File

1. **Update it regularly** — add new tables, components, and conventions as your project grows
2. **Keep it honest** — document known issues and tech debt, not just the happy path
3. **Don't make it too long** — if it's over 200 lines, trim the less important parts. AI reads the whole thing, and too much context can be diluting
4. **Review after major changes** — if you refactored the project structure or switched a library, update this file
5. **Version it with your code** — commit this file to Git so it stays in sync with your project

> 💡 **This file is one of the most valuable things in your project.** A well-maintained rules file means every AI conversation starts with full context about your project. It's the difference between AI guessing what you want and AI knowing what you need.
