# Chapter 10: Does My App Actually Work? (Evaluation)

You've built something. It has buttons, pages, maybe even a login screen. That's amazing! 🎉

But here's the big question: **does it actually work?**

Not "does it work on your laptop, on your screen, with your internet connection, when you click things in the exact right order." Does it work for *real people* in the *real world*?

This chapter is all about making sure your app is ready for other humans to use — and trust. We'll cover everything from simple manual checks you can do yourself, to getting AI to write automated tests, to watching real people try your app for the first time (which is both terrifying and incredibly valuable).

By the end of this chapter, you'll have a complete toolkit for making sure your app doesn't just *exist* — it actually *works*.

Let's dive in. 🏊‍♂️

---

## Why Testing Matters (Even for MVPs)

Here's an analogy: **you wouldn't sell a car without test-driving it first.** Even if it's a basic model with no fancy features, it still needs to start, steer, and stop. Those are non-negotiable.

Your app is the same way. Even a Minimum Viable Product — the simplest version of your idea — needs to actually *work*. The "minimum" part refers to features, not quality. You can launch with fewer features, but the features you *do* have need to be solid.

Here's another way to think about it: imagine you open a new restaurant. Your menu only has five items — that's fine for an MVP. But if the food is undercooked, the chairs are broken, and the bathroom door doesn't lock? Nobody's coming back. The *scope* can be small, but the *quality* needs to be there.

**Why does this matter so much?**

- **Bugs kill trust faster than missing features.** If someone signs up and the page crashes, they're gone. They won't come back to check if you fixed it next week. But if your app works smoothly and just doesn't have dark mode yet? They'll live with that.
- **First impressions are everything.** You often get one shot with a new user. A broken experience tells them, "This person doesn't care about quality." A smooth experience — even a simple one — tells them, "This person has their act together."
- **You'll save yourself time.** Finding bugs *before* you share your app is a hundred times easier than debugging a problem while panicked users are emailing you about it.

> 💡 **Think of it this way:** Testing isn't about being a perfectionist. It's about being respectful of the people who are going to spend their time trying your app.

Think about apps you've stopped using. Was it because they didn't have enough features? Probably not. It was more likely because something didn't work right, felt clunky, or frustrated you. That's exactly what you want to prevent.

The good news? You don't need to be a professional software tester. You don't need to write complicated scripts or understand fancy testing frameworks. You just need a checklist, some honest friends, and a little patience.

---

## Manual Testing Checklist for Non-Coders

Before you show your app to anyone — and definitely before you launch — walk through this checklist yourself. Open your app and go through each item one by one. Be honest with yourself.

Grab a notepad (or open a notes app) and write down anything that feels off. Don't try to fix things while you're testing — just observe and take notes. This separation is important: testing mode and fixing mode are two different mindsets. If you try to fix things as you find them, you'll lose track of what else needs checking.

**How to go through this checklist:**
1. Open your app in a browser
2. Start at item #1 and work your way down
3. For each item, write "✅ Pass" or "❌ Fail — [what went wrong]"
4. After you finish the whole list, *then* go back and fix the failures
5. After fixing, test those items again to make sure the fixes worked

### ✅ The 15-Point Manual Testing Checklist

- [ ] **1. All buttons work and go to the right place**
  Click every single button in your app. Does each one do what it says? Does "Sign Up" go to the signup page? Does "Submit" actually submit? Does "Back" go back? You'd be surprised how often buttons lead nowhere.

- [ ] **2. Forms submit correctly (with both valid AND invalid data)**
  Fill out every form in your app with correct information first — does it work? Great. Now try breaking it: leave fields empty, enter a fake email like "asdf", type letters in a phone number field. Does your app handle these mistakes gracefully, or does it blow up?

- [ ] **3. Mobile view looks good (test on a real phone)**
  Don't just resize your browser window. Actually pull up your app on your phone. Is everything readable? Can you tap buttons without accidentally hitting the wrong one? Does the layout make sense on a small screen? More than half of web traffic comes from phones — this matters.

- [ ] **4. Loading speed is acceptable (under 3 seconds)**
  Open your app on a regular internet connection (not your super-fast home Wi-Fi). Does it load quickly? If people are staring at a blank screen for more than 3 seconds, many of them will leave. You can test this at [PageSpeed Insights](https://pagespeed.web.dev/) for free.

- [ ] **5. Edge cases work (empty states, very long text, special characters)**
  What happens when there's no data to show? (Like an empty dashboard when you first sign up.) What happens if someone types a really, really long name? What about special characters like é, ñ, or emojis? These "edge cases" are where a lot of apps break.

- [ ] **6. Images load properly**
  Check every image in your app. Are any showing as broken icons? Do they load quickly enough? Do they look good on both desktop and mobile? Missing or broken images make your app look unfinished.

- [ ] **7. Links don't go to 404 pages**
  Click every link. Every single one. Does each link take you where it should? A "Page Not Found" error is one of the quickest ways to make your app feel broken or abandoned.

- [ ] **8. Error messages are helpful (not technical jargon)**
  When something goes wrong, what does the user see? If your error message says `TypeError: Cannot read property 'map' of undefined`, that means nothing to a normal person. Errors should say things like "Something went wrong. Please try again." or "Please enter a valid email address."

- [ ] **9. The app works in different browsers (Chrome, Safari, Firefox)**
  Your app might look perfect in Chrome but broken in Safari (this is more common than you'd think). Open your app in at least Chrome, Safari (if you have a Mac or iPhone), and Firefox. Check that things look and function the same.

- [ ] **10. Login/signup flow works end to end**
  If your app has accounts, test the entire flow: sign up with a new account, verify your email (if needed), log in, log out, log back in, reset your password. Every step. This is one of the first things new users experience, so it has to be flawless.

- [ ] **11. Payment flow works (if applicable)**
  If you're charging money, this is *critical*. Test it in "test mode" if your payment provider offers it (Stripe, for example, has test credit card numbers). Make sure the payment goes through, the user gets access to what they paid for, and they receive a confirmation. Money is where trust matters most.

- [ ] **12. Data saves and persists (refresh the page)**
  Enter some data into your app. Now refresh the page. Is the data still there? If your users create something — a profile, a list, a project — and it disappears when they close their browser, that's a serious problem.

- [ ] **13. Navigation makes sense (can users find things?)**
  Pretend you've never seen your app before. Can you figure out how to do the main thing the app is for? Is the menu clear? Are important actions easy to find? If you have to think hard about where something is, your users will struggle too.

- [ ] **14. Accessibility basics (can you tab through? readable fonts?)**
  Try navigating your app using only your keyboard (Tab to move between elements, Enter to click). Can you reach everything? Also check: are your fonts big enough to read comfortably? Is there enough contrast between text and background colors? Accessibility isn't just nice to have — it means more people can use your app.

- [ ] **15. The "happy path" works perfectly**
  The "happy path" is the main thing your app is designed to do — the core use case. If your app is a to-do list, the happy path is: create a task, see it on the list, mark it done. Whatever your version of that is, it needs to work *flawlessly*. This is the thing people came for.

> 🎯 **Pro tip:** Go through this checklist at least twice — once quickly to catch the obvious stuff, and once slowly and deliberately to catch the subtle stuff.

---

## Asking AI to Write Tests for You

Here's something exciting: you don't have to learn how to write code tests yourself. You can ask your AI coding assistant to write them for you!

### What Are Automated Tests?

Think of automated tests as little robot helpers that check your app for you. Instead of you manually clicking every button, these tests are small scripts that do the clicking automatically and tell you if something broke.

It's like having a tiny quality inspector who works for free and never gets tired. They'll check the same things over and over, every time you make a change, to make sure nothing broke.

You don't need to understand how the test code works under the hood. Your AI assistant writes the code; you just need to know how to run it and read the results. Most test output is simple: green checkmarks mean things passed, red X marks mean something broke. That's really it.

### The Big Benefit of Automated Tests

Here's the *real* reason automated tests are worth it: **they protect you from accidentally breaking things.**

Let's say your signup form works great today. Next week, you ask your AI to add a new feature to the homepage. Without realizing it, that change might break the signup form. If you have automated tests, they'll catch that immediately. Without them, you might not find out until a frustrated user tells you — or worse, just leaves.

Tests are like a safety net for your code. They let you move faster *because* they catch your mistakes.

### How to Ask AI to Write Tests

The key is to be specific about what you want tested. Here are some prompts you can copy and paste:

**For a signup form:**

```
Write tests for my signup form that check:
- Email validation (invalid emails are rejected)
- Empty fields show error messages
- Passwords must be at least 8 characters
- Successful submission redirects to the dashboard
- Duplicate email addresses show a helpful error
```

**For a search feature:**

```
Write tests for my search bar that check:
- Searching with a valid term returns results
- Searching with no results shows a friendly "no results" message
- The search works with special characters
- Empty search shows all items (or an appropriate message)
- Results match what was searched for
```

**For a payment page:**

```
Write tests for my checkout flow that check:
- The correct total is displayed
- Required fields are validated before submission
- A successful payment shows a confirmation
- An invalid credit card shows a clear error message
- The user can go back and edit their cart
```

**For navigation:**

```
Write tests that check all the links in my navigation menu:
- Each menu item links to the correct page
- The current page is highlighted in the menu
- The menu works on mobile (hamburger menu opens and closes)
- The logo links back to the homepage
```

> 💡 **Don't worry** if you don't understand the test code the AI generates. What matters is that you can *run* the tests and see if they pass or fail. Ask your AI assistant: "How do I run these tests?" and it'll walk you through it.

### When Should You Ask for Tests?

- After building any new feature
- Before sharing your app with others
- Before launching publicly
- After fixing a bug (to make sure it doesn't come back)
- When you're about to make big changes (tests protect what already works)

### What to Do When Tests Fail

Don't panic! A failing test is actually *good news* — it means you caught a problem before your users did. Here's what to do:

1. Read the test output. It usually tells you *what* failed and sometimes *why*.
2. Copy the error message and paste it to your AI assistant.
3. Ask: "This test is failing. Can you help me understand why and fix it?"
4. Run the tests again after the fix to make sure everything passes.

Think of failing tests like a smoke detector going off. Yes, it's loud and annoying, but it's much better than the alternative.

---

## The "Fresh Eyes" Test

This might be the most important test of all, and it doesn't involve any technology.

**Hand your app to someone who has never seen it before and watch them try to use it.**

That's it. That's the test.

### Why This Matters

You are the worst person to test your own app. Seriously! You built it. You know where everything is. You know the "right" way to use it. You'll unconsciously avoid the things that are broken because you already know about them.

A fresh pair of eyes will find problems in 30 seconds that you've been blind to for weeks.

### The "Watch, Don't Help" Rule 🤐

This is crucial and really hard: **when someone is testing your app, do not help them.** Don't say "oh, you need to click *there*" or "that button is actually on the other page." Just watch.

If they get stuck, let them struggle for a moment. Watch *where* they look, *what* they try to click, and *when* they hesitate. These moments of confusion are pure gold — they tell you exactly where your app needs to be clearer.

If they can't figure something out, that's not their failure — it's your app's failure. Write it down and fix it later.

If you absolutely can't resist helping, try redirecting instead of answering: "What would you try?" or "What are you looking for?" This keeps the test authentic while giving you even more insight into how people think about your app.

### Your Fresh Eyes Testing Script

Here's exactly what to say when you ask someone to test your app:

> "Hey, I built this app and I'd love your honest feedback. I'm going to give you the link and ask you to try to [main thing the app does]. I won't give you any instructions — I want to see if it makes sense on its own. Please think out loud and tell me what you're seeing, what you expect, and any confusion. There are no wrong answers, and you can't hurt my feelings. Be brutal!"

**Then ask these follow-up questions:**

1. "What did you think this app was for when you first saw it?"
2. "Was anything confusing or unclear?"
3. "Did anything not work the way you expected?"
4. "What would you change if you could change one thing?"
5. "Would you use this? Why or why not?"

### How Many People Should You Test With?

Research shows that **5 people will find about 85% of usability problems.** You don't need a huge focus group. Ask 3–5 people and you'll learn more than you expect.

### Picking the Right Testers

Not all testers are created equal. Ideally, you want people who resemble your *actual target audience*. If you're building an app for small business owners, testing with your developer friend might not surface the same issues that a non-technical shop owner would encounter.

That said, *any* fresh eyes are better than no fresh eyes. Don't let the search for perfect testers stop you from testing at all.

### What to Do With the Feedback

After your fresh eyes testing sessions, you'll probably have a long list of issues. Here's how to prioritize:

1. **Fix anything that's actually broken** (crashes, errors, data loss) — these are urgent
2. **Fix major confusion points** (people couldn't figure out how to do the main thing) — these are important
3. **Note nice-to-have improvements** (things that would be smoother or prettier) — save these for later
4. **Ignore personal preferences** ("I'd make the button blue instead of green") — unless multiple people say the same thing

---

## User Testing on a Budget

You don't need to hire a fancy research firm. Here's how to get real feedback for free (or close to it):

### Free Options

- **Friends and family** — Start here, but keep in mind they might be too nice. Ask them to be brutally honest and remind them that it helps you more.
- **Coworkers or acquaintances** — People who like you enough to help but aren't so close that they'll sugarcoat everything.
- **Reddit communities** — Subreddits like r/SideProject, r/startups, r/webdev, r/design_critiques, and r/roastmystartup are full of people who will give you honest (sometimes *very* honest) feedback.
- **Indie Hackers** — The community at [indiehackers.com](https://www.indiehackers.com) is incredibly supportive of solo builders. Share what you're building and ask for feedback.
- **Twitter/X and LinkedIn** — Post a short demo or link and ask for feedback. You might be surprised how many people are willing to help.
- **Discord communities** — Many niche communities have channels for sharing projects and getting feedback.
- **Facebook groups** — There are groups for almost every niche imaginable. Find one that matches your target audience and share your app there.

### Tips for Getting Better Feedback

Here are a few extra tips that'll help you get the most useful responses:

- **Set a time limit.** Ask people to spend just 5–10 minutes. This respects their time and gives you focused feedback.
- **Ask one specific question.** Instead of "what do you think?", try "can you figure out how to create a new project?" Specific tasks get specific feedback.
- **Offer to return the favor.** Many indie builders are happy to swap — you test theirs, they test yours.
- **Don't take it personally.** Every critique is about the *app*, not about you. The sooner you internalize this, the faster you'll improve.
- **Follow up with thanks.** When someone takes time to give you feedback, thank them genuinely. Let them know what you fixed based on their input. This builds relationships and makes them more likely to help again.

### Cheap Options

- **ProductHunt** — Launching on ProductHunt is free and gets your app in front of thousands of tech-savvy early adopters who love giving feedback.
- **Beta testing platforms** — Sites like BetaList let you list your app for early adopters to try.
- **Coffee shop testing** — Offer to buy someone a coffee in exchange for 10 minutes of trying your app. Real-world testing at its finest.

### How to Ask for Feedback Effectively

Bad way to ask:
> "Hey check out my app, what do you think?"

This gets you vague answers like "looks cool!" which doesn't help.

**Good way to ask:**
> "I built an app that helps [specific audience] do [specific thing]. Could you try to [specific task] and let me know if anything was confusing or broken? I'm specifically looking for honest criticism — it helps me the most."

The more specific your ask, the more useful the feedback.

### Handling Negative Feedback

This part is hard but important: **negative feedback is a gift.** 🎁

When someone says "this was confusing" or "I didn't know what to click," they're giving you a roadmap to making your app better. The temptation is to explain or defend your choices — resist it. Just say "thank you, that's really helpful" and write it down.

Remember, every piece of critical feedback you get now is one less frustrated user after launch. The people who take time to point out problems are doing you a huge favor.

---

## Common Quality Issues in Vibe-Coded Apps

When you build with AI assistance, certain types of bugs tend to pop up more often than others. This isn't a knock on AI — it's just the nature of generating code from prompts. Knowing what to look for means you can catch these issues early.

Here's your "usual suspects" list:

### 🔗 Broken Links and Dead Ends
AI sometimes generates links to pages that don't exist yet, or references routes that were renamed. Click *every* link in your app.

### 📱 Missing Mobile Responsiveness
AI-generated layouts often look great on desktop but fall apart on mobile. Text overflows, buttons stack weirdly, images stretch. Always check the mobile view.

### 🐌 Slow Loading Times
AI might pull in large libraries or unoptimized images without you realizing it. If your app feels slow, ask your AI assistant: "How can I improve the loading speed of my app?"

### ❌ Poor Error Handling
This is one of the most common issues. When something goes wrong (and something *will* go wrong), your app should show a friendly message — not crash, show a blank screen, or display technical error codes.

### 🎨 Inconsistent Styling
When you build different parts of your app at different times, or with different AI prompts, styling can get inconsistent. Fonts, colors, spacing, and button styles might vary from page to page. Look at your app as a whole — does it feel like one product or a patchwork?

### ⏳ Missing Loading States
When your app is fetching data or processing something, users need to see *something* — a spinner, a skeleton screen, a progress bar. If they click a button and nothing visibly happens for 2 seconds, they'll click it again (and again), which can cause problems.

### 📝 Forms That Don't Validate
AI-generated forms often skip validation. That means users can submit empty forms, enter garbage data, or miss required fields without any warning. Always ask your AI: "Add validation to this form so users can't submit invalid data."

### 🔒 Missing or Broken Authentication Edge Cases
Login might work, but what about: logging out and trying to access a protected page? What if the session expires? What if someone bookmarks a page they need to be logged in to see?

### 🔄 State Management Quirks
Sometimes AI-generated apps don't properly sync state across the app. For example, you update your profile name but the header still shows the old name until you refresh. Or you delete an item from a list, but it still appears until you navigate away and come back. Ask your AI: "Make sure changes in [feature] are reflected immediately everywhere in the app."

### 📋 Copy-Paste and Keyboard Issues
Users might want to paste text into forms, use keyboard shortcuts, or select text. AI-generated apps sometimes accidentally prevent these basic interactions. Try copying and pasting into every input field in your app.

### 🌐 Internationalization Gaps
If any of your users might have names with accents (José, François, Müller) or use non-English characters, test with those. AI-generated apps sometimes choke on characters outside the basic English alphabet. Even if you're only targeting English speakers, people have diverse names.

> ⚡ **Quick fix:** If you spot any of these, don't panic. Just describe the problem to your AI assistant and ask it to fix it. That's the beauty of vibe coding — the same AI that helped you build it can help you fix it. Try a prompt like: "I found these issues in my app: [list the issues]. Can you fix them one by one?"

---

## Quality Checklist Template

Here it is — your copy-paste quality checklist. Use this before every launch, every major update, and every time you share your app with new people.

Copy this into a document, a Notion page, a Google Doc, or wherever you track things, and check items off as you go. Some teams print it out and physically check items off with a pen — whatever works for you.

> 💡 **How to use this checklist:** Don't try to do everything in one sitting. Break it into sessions — maybe core functionality in the morning, visual checks after lunch, and fresh eyes testing the next day. The goal is to be thorough, not to burn yourself out.

> 🔁 **Make it a habit:** After a few launches, you'll start catching these issues *while* you build, before you even need the checklist. That's the sign of a builder who takes quality seriously.

---

### 🚀 Pre-Launch Quality Checklist

**Core Functionality**
- [ ] The main feature (happy path) works perfectly from start to finish
- [ ] All buttons do what they're supposed to do
- [ ] All links go to the right pages (no 404 errors)
- [ ] Forms validate input and show helpful error messages
- [ ] Data saves correctly and survives a page refresh
- [ ] Search works (if applicable)
- [ ] Filtering/sorting works (if applicable)

**User Accounts (if applicable)**
- [ ] Signup works with valid information
- [ ] Signup rejects invalid information with clear messages
- [ ] Login works correctly
- [ ] Logout works correctly
- [ ] Password reset flow works end to end
- [ ] Protected pages redirect to login when not authenticated
- [ ] User data is tied to the right account

**Payments (if applicable)**
- [ ] Checkout flow works end to end
- [ ] Correct amounts are displayed
- [ ] Payment confirmation is shown
- [ ] Failed payments show helpful error messages
- [ ] Users get access to what they paid for

**Visual & Mobile**
- [ ] App looks good on desktop (at least 1280px wide)
- [ ] App looks good on tablet
- [ ] App looks good on mobile phone (test on a real device)
- [ ] Images load correctly and look sharp
- [ ] No text is cut off or overlapping
- [ ] Fonts are readable (not too small)
- [ ] Colors have enough contrast
- [ ] No horizontal scrolling on mobile

**Performance & Reliability**
- [ ] Pages load in under 3 seconds
- [ ] No console errors in the browser (right-click → Inspect → Console tab)
- [ ] App works in Chrome
- [ ] App works in Safari
- [ ] App works in Firefox
- [ ] App works with slow internet (try throttling in browser dev tools)
- [ ] Large data sets don't break the app (what happens with 100+ items?)
- [ ] Refreshing any page works (no crashes on reload)

**User Experience**
- [ ] Navigation is clear and intuitive
- [ ] Empty states have helpful messages (not blank screens)
- [ ] Loading states are visible (spinners or progress indicators)
- [ ] Error messages are friendly and human-readable
- [ ] Users can accomplish the main task without instructions
- [ ] The app is accessible via keyboard navigation (Tab + Enter)
- [ ] Confirmation messages appear after important actions (save, delete, submit)
- [ ] Users can undo or go back from any action

**Content & Polish**
- [ ] No placeholder text left in (like "Lorem ipsum" or "TODO")
- [ ] No spelling or grammar errors
- [ ] App name and branding are consistent
- [ ] Favicon is set (the little icon in the browser tab)
- [ ] Page titles are meaningful (not "React App" or "Untitled")
- [ ] Social sharing looks good (try pasting your URL into a chat — does a nice preview show up?)
- [ ] Copyright year is current
- [ ] Contact or support information is available

**Fresh Eyes Test**
- [ ] At least 3 people have tried the app without instructions
- [ ] Major confusion points have been addressed
- [ ] Feedback has been documented for future improvements

**Security Basics**
- [ ] No passwords or API keys are visible in the code or on the page
- [ ] User data is only visible to the right user (not leaking to others)
- [ ] HTTPS is enabled (the URL starts with `https://`, not `http://`)
- [ ] Sensitive actions (delete, payment) ask for confirmation
- [ ] Session expires appropriately (users aren't logged in forever)
- [ ] File uploads (if any) are restricted to expected types and sizes

---

## What's Next?

You've tested your app, squashed the bugs, and gotten real feedback from real people. Your app is solid. 💪

But here's the thing — evaluation isn't a one-time event. Every time you add a feature or make a change, come back to this checklist. Make it a habit. Your future self (and your users) will thank you.

The best apps in the world aren't the ones that launched perfectly — they're the ones that kept listening, kept testing, and kept improving. That's what separates a weekend project from a real product.

> 🌟 **Remember:** A simple app that works beautifully will always beat a complex app that's full of bugs. Quality over quantity, every single time.

You don't need to be a QA engineer. You don't need fancy testing tools. You just need to care enough to check your work — and you clearly do, because you read this whole chapter.

Now go test that app. You've got this! 🚀
