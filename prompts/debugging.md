# 🐛 Prompts for Debugging

> Bugs happen to everyone — even experienced developers. The secret isn't avoiding bugs, it's getting really good at squishing them. These prompts will help you use AI to find and fix problems fast. Swap out the `[placeholders]` with your own details!

---

## Fixing Errors

### 1. The "I have no idea what's wrong" prompt

```
My app is broken and I don't know why. Here's what's happening:

- What I expected: [describe what should happen]
- What actually happens: [describe what you see instead]
- When it started: [when did it break? after what change?]

Here's the error message (if any):
[paste the error message]

Here's the relevant code:
[paste your code]

Please:
1. Explain what's going wrong in plain English
2. Show me exactly how to fix it
3. Explain WHY the fix works so I understand for next time
```

### 2. Fix a specific error message

```
I'm getting this error and I don't understand it:

[paste the full error message, including any stack trace]

My code looks like this:
[paste the relevant code]

I'm using [list your tools: React, Next.js, Supabase, etc.].

Can you:
1. Translate this error into plain English — what is it actually saying?
2. Point to the exact line or lines causing the problem
3. Show me the fix
4. Tell me how to prevent this type of error in the future
```

### 3. "It works sometimes but not always"

```
I have a weird bug — my [feature] works sometimes but not other times.

Here's what I've noticed:
- It works when: [describe the conditions]
- It breaks when: [describe the conditions]
- It started happening after: [what changed?]

Here's the code:
[paste your code]

What could cause this inconsistent behavior? Walk me through how to
diagnose it step by step.
```

---

## Understanding Error Messages

### 4. Decode a confusing error

```
I'm a beginner and I have no idea what this error means. Can you explain
it to me like I'm 10 years old?

Error:
[paste the error]

What does each part of this error mean? What is the computer actually
trying to tell me? And what's the most common cause?
```

### 5. Learn to read stack traces

```
I keep seeing these "stack traces" when my app crashes, and they look
like gibberish to me. Here's one:

[paste the stack trace]

Can you teach me how to read this? Walk me through it line by line:
- Which line is the actual error?
- Which lines show where the error came from?
- Which lines can I usually ignore?
- How do I find MY code vs. library code in the stack trace?
```

---

## Troubleshooting Performance

### 6. My app is slow

```
My [app/page/feature] is really slow. It takes about [X seconds] to
[describe the action, e.g., "load the dashboard" or "save a form"].

Here's my code:
[paste the relevant code]

Can you:
1. Identify what's making it slow (in plain English)
2. Suggest the easiest fixes to speed it up
3. Rank the fixes from "biggest impact" to "nice to have"
4. Show me the updated code for the top fix

I'm using [list your tech stack]. I'm a beginner, so keep the solutions
simple.
```

### 7. Find and fix memory/performance leaks

```
My app gets slower the longer someone uses it, or the browser tab eventually
crashes. I think there might be a memory leak.

Here's the code for the main components that stay on screen:
[paste your code]

Can you:
1. Spot any potential memory leaks or performance problems
2. Explain what a memory leak is (simply!) and why it matters
3. Show me the fixes
4. Tell me how to use browser DevTools to check if it's fixed

Keep the explanation beginner-friendly.
```

---

## Fixing Layout Problems

### 8. My layout looks broken

```
My [page/component] layout is messed up. Here's what's happening:

- [Describe the visual problem: "the sidebar overlaps the content,"
  "there's a weird gap at the bottom," "the text is cut off," etc.]
- It happens on [desktop/mobile/both]

Here's my code:
[paste the HTML/JSX and CSS/Tailwind classes]

Please:
1. Explain what's causing the layout issue
2. Fix it
3. If I'm using Tailwind, show me the correct utility classes
4. Suggest a mental model for how [flexbox/grid/whatever is relevant]
   works so I can avoid this next time
```

### 9. My page looks different on different browsers/devices

```
My app looks great on [browser/device where it works] but looks broken
on [browser/device where it doesn't].

Here's what's different:
- On [working browser]: [describe how it looks]
- On [broken browser]: [describe how it looks]

Here's the code:
[paste your code]

What browser compatibility issues might be causing this? Show me the
fixes and explain which CSS features have spotty browser support.
```

---

## Asking AI for Help Effectively

### 10. Debug with the "rubber duck" approach

```
I'm stuck on a bug and I need to think through it out loud. I'll describe
everything, and you help me figure it out by asking good questions.

Here's my app: [brief description]
Here's what's broken: [describe the problem]
Here's what I've tried so far:
- [thing 1] — result: [what happened]
- [thing 2] — result: [what happened]

Don't give me the answer yet. Instead, ask me 3-5 questions that will
help me narrow down where the bug is. Guide me like a patient teacher.
```

### 11. Systematic debugging checklist

```
I have a bug in my [type of app]. Before I spend hours randomly changing
things, give me a systematic debugging checklist for this situation:

The problem: [describe what's going wrong]
My tech stack: [list your tools]
What I've tried: [list what you've done]

Create a step-by-step checklist I can follow, starting from the simplest
things to check (like "is it saved?" and "did you refresh?") to more
advanced debugging. For each step, tell me exactly what to do and what
to look for.
```

### 12. Compare what changed

```
My app was working fine yesterday. Today it's broken. I'm not sure what
I changed.

Here's the error:
[paste the error]

Here's what I remember changing:
- [change 1]
- [change 2]

Can you help me figure out which change broke it? For each change I
listed, explain whether it could cause this specific error and why.
Then tell me how to use Git to see exactly what changed (I'm a Git
beginner — be very specific with the commands).
```

### 13. "Fix it AND teach me"

```
Here's my broken code:

[paste your code]

Error: [paste the error]

I want you to do TWO things:
1. Fix the code (show me the corrected version)
2. Add comments in the code explaining WHAT was wrong and WHY the fix
   works — so I can learn from this mistake and never make it again

I'm a beginner at [your tech stack], so keep explanations simple.
```

---

## 💡 Tips for Better Debugging

- **Copy the FULL error message.** Don't paraphrase it. The exact text matters — every word is a clue.
- **Include your code.** The AI can't help if it can't see what you wrote. Always paste the relevant code.
- **Say what you expected vs. what happened.** "It's broken" isn't enough. Be specific about the gap between expected and actual behavior.
- **Mention what you changed recently.** Bugs almost always come from recent changes. Think back: what did you add, remove, or modify?
- **Don't change 5 things at once.** Make one fix, test it, then try the next fix. Otherwise you'll never know what worked.
- **Use your browser's DevTools.** Right-click → Inspect → Console tab. Errors show up in red. This is your best friend.

---

*Part of [The Vibe Coding Playbook](../README.md) — a guide for building real apps with zero coding experience.*
