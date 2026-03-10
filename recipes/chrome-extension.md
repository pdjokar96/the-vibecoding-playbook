# 🧩 Recipe: Your First Chrome Extension

> Build a handy productivity extension — a Quick Notes sidebar that lets you jot down notes on any webpage — and publish it to the Chrome Web Store. No coding experience needed.

---

## At a Glance

| Detail | Info |
|---|---|
| **Difficulty** | 🟢 Beginner |
| **Time Estimate** | 1.5–2 hours |
| **Tools Needed** | AI coding assistant (Cursor, GitHub Copilot, or Bolt), Google Chrome browser, a Google Developer account ($5 one-time fee to publish — optional) |
| **Prerequisites** | A computer with Chrome installed. That's it! |
| **What You'll Build** | A Chrome extension that opens a sidebar where you can quickly write, save, and organize notes — right inside your browser |

---

## Before You Start

1. **Open Google Chrome** — This recipe is Chrome-specific (it'll also work for Edge with small tweaks).
2. **Open your AI coding tool** — Have it ready to go.
3. **Create a project folder** — Make a new folder on your computer called `quick-notes-extension`. This is where all your files will live.

💡 **How Chrome extensions work (the 30-second version):** A Chrome extension is just a small collection of web files (HTML, CSS, JavaScript) plus a special file called `manifest.json` that tells Chrome what your extension does. That's it — no servers, no databases, no deployment. Chrome reads the files directly from your computer (or from the Chrome Web Store).

---

## Step 1: Create the Manifest File

The manifest is like your extension's ID card — it tells Chrome everything it needs to know.

> **Prompt:**
>
> Create a `manifest.json` file for a Chrome extension called "Quick Notes." Here are the details:
>
> - **Name:** Quick Notes
> - **Description:** Jot down quick notes on any webpage. Your notes are saved locally and always available.
> - **Version:** 1.0.0
> - **Manifest version:** 3 (the latest standard)
>
> The extension should:
> - Have a browser action (toolbar icon) that opens a popup
> - Have a side panel where the main notes interface lives
> - Use Chrome's storage API to save notes locally
> - Request only the minimum permissions needed
>
> Also create a simple 128x128 icon. Since I don't have a custom icon yet, generate an SVG icon with a notepad/pencil design and create PNG versions at 16x16, 48x48, and 128x128 sizes. (Or just tell me where to get free icons.)

✅ **What to check:** You should have a `manifest.json` file in your project folder. Don't worry if it's not perfect — we'll test it soon.

---

## Step 2: Build the Popup Interface

The popup is the small window that appears when you click your extension's icon.

> **Prompt:**
>
> Create the popup for my Quick Notes Chrome extension. I need these files:
>
> - `popup.html` — the popup UI
> - `popup.css` — styles
> - `popup.js` — functionality
>
> The popup should:
> - Be 350px wide and 500px tall
> - Have a clean header with "Quick Notes" title and a small "+" button to add a new note
> - Show a list of saved notes, with the most recent at the top
> - Each note should display a preview (first 50 characters) and the date it was saved
> - Clicking a note opens it for editing
> - Clicking "+" creates a new blank note
> - Include a simple text area for writing/editing notes
> - Have a "Save" button and a "Delete" button for each note
> - Use Chrome's `chrome.storage.local` API to save and load notes
> - Style it beautifully — clean, minimal, modern design with soft colors
>
> Make the notes persist — when I close and reopen the popup, my notes should still be there.

✅ **What to check:** Don't test it yet — let's get all the files created first, then we'll load the extension.

---

## Step 3: Add Search and Organization

> **Prompt:**
>
> Upgrade the Quick Notes popup with these features:
>
> 1. **Search bar** at the top — filters notes in real time as you type
> 2. **Color labels** — let me assign a color to each note (choose from 5 preset colors like yellow, blue, green, pink, purple). Show a small color dot next to each note in the list.
> 3. **Character count** — show a character count at the bottom of the text area when editing
> 4. **Keyboard shortcuts:**
>    - `Ctrl+S` (or `Cmd+S` on Mac) to save the current note
>    - `Escape` to go back to the notes list
> 5. **Empty state** — when there are no notes, show a friendly message like "No notes yet! Click + to create your first one."
>
> Keep the clean, minimal design. Make sure everything still works with `chrome.storage.local`.

---

## Step 4: Add a Context Menu Option

This lets you right-click on selected text on any webpage and save it as a note!

> **Prompt:**
>
> Add a right-click context menu to my Quick Notes extension:
>
> 1. Create a `background.js` (service worker) file
> 2. When I select text on any webpage and right-click, show an option that says "Save to Quick Notes"
> 3. Clicking it should save the selected text as a new note, along with the page URL and title
> 4. Show a small notification (Chrome notification API) confirming "Note saved!"
> 5. Update the `manifest.json` to include the background service worker and any new permissions needed (like `contextMenus` and `notifications`)
>
> The saved note should appear in my popup notes list like any other note, with a small link icon showing it came from a webpage.

---

## Step 5: Test the Extension Locally

Now let's load your extension into Chrome and try it out!

> **Prompt:**
>
> Give me step-by-step instructions to load and test my Chrome extension locally:
>
> 1. How to open Chrome's extension management page
> 2. How to enable Developer Mode
> 3. How to load my unpacked extension from my project folder
> 4. How to test each feature
> 5. How to see error messages if something goes wrong (where's the console?)
> 6. How to reload the extension after making changes

Here's the short version:

1. Open Chrome and go to `chrome://extensions/`
2. Toggle **"Developer mode"** on (top right corner)
3. Click **"Load unpacked"**
4. Select your `quick-notes-extension` folder
5. You should see your extension appear! Click the puzzle piece icon in the toolbar to find it.

✅ **What to check:**
- Click the extension icon — does the popup appear?
- Create a new note, type something, and save it
- Close the popup and reopen it — is your note still there?
- Try the search bar
- Try right-clicking selected text on a webpage — does "Save to Quick Notes" appear?

---

## Step 6: Fix Any Issues

It's totally normal for things not to work perfectly on the first try. Here's how to debug:

> **Prompt:**
>
> I loaded my Chrome extension and [describe what's wrong — e.g., "the popup is blank," "notes aren't saving," "the context menu doesn't appear," etc.]. Here is the error from the console:
>
> [Paste any error messages you see]
>
> Here are my current files:
>
> [Paste the relevant file contents]
>
> Help me fix this.

💡 **Tip:** To see error messages, go to `chrome://extensions/`, find your extension, and click **"Inspect views"** next to "service worker" or right-click your popup and select "Inspect." Check the Console tab for red error messages.

---

## Step 7: Add Polish and Final Touches

> **Prompt:**
>
> Do a final polish pass on my Quick Notes extension:
>
> 1. **Smooth animations** — add subtle fade-in animations when notes appear and transition effects when switching between list view and edit view
> 2. **Auto-save** — automatically save the note as I type (with a small "Saved" indicator), so I don't have to click the Save button every time
> 3. **Export notes** — add an "Export All" option in a settings menu that downloads all notes as a JSON file (for backup)
> 4. **Import notes** — add an "Import" option that loads notes from a previously exported JSON file
> 5. **Dark mode** — detect the system theme and automatically switch between light and dark mode
> 6. Make sure the extension icon looks good in both light and dark browser themes

---

## Step 8: Create Promotional Assets (For Chrome Web Store)

Skip this step if you just want the extension for personal use!

> **Prompt:**
>
> Help me prepare my Chrome extension for the Chrome Web Store. I need:
>
> 1. A detailed description for the store listing (highlight all features, use bullet points, keep it under 500 words)
> 2. A list of what to put in the "Privacy practices" section (my extension only stores data locally — no data is sent to any server)
> 3. A privacy policy (even though we don't collect data, the store requires one). Generate a simple, honest privacy policy that says we store notes locally and don't collect or transmit any personal data.
> 4. Instructions for creating screenshots of the extension (what dimensions does the Chrome Web Store require?)
> 5. A step-by-step guide to submitting the extension for review

Here's what you'll need for the Chrome Web Store:

| Asset | Requirements |
|---|---|
| Screenshots | 1280x800 or 640x400 pixels, at least 1, up to 5 |
| Small promo tile | 440x280 pixels |
| Icon | 128x128 pixels (you already have this!) |
| Description | Up to 16,000 characters |
| Privacy policy | A URL to your privacy policy |

---

## Step 9: Publish to the Chrome Web Store

> **Prompt:**
>
> Walk me through publishing my Chrome extension to the Chrome Web Store, step by step:
>
> 1. How to create a ZIP file of my extension
> 2. How to sign up for a Chrome Web Store developer account (one-time $5 fee)
> 3. How to upload my extension
> 4. How to fill out all the required fields
> 5. How to submit for review
> 6. How long does review typically take?
> 7. What are common rejection reasons and how to avoid them?

### Quick Summary

```bash
# Create a ZIP file of your extension (from inside your project folder)
# On Windows:
# Right-click the folder → "Send to" → "Compressed (zipped) folder"

# On Mac/Linux:
zip -r quick-notes-extension.zip . -x ".*" -x "__MACOSX"
```

Then:
1. Go to the [Chrome Web Store Developer Dashboard](https://chrome.google.com/webstore/devconsole)
2. Pay the one-time $5 registration fee
3. Click **"New Item"** and upload your ZIP file
4. Fill in the store listing, upload screenshots, and set the privacy policy
5. Submit for review (usually takes 1–3 business days)

---

## 🎉 You Did It!

You just built a real Chrome extension — a genuinely useful productivity tool — and you can publish it for the whole world to use. That's pretty incredible for someone who started with zero coding experience.

### What to Do Next

- **Use your own extension!** Pin it to your toolbar and start taking notes
- **Share it** with friends and get feedback
- **Add more features** — maybe a way to sync notes across devices using Supabase (combine this recipe with the [Waitlist recipe](./saas-waitlist.md)!)
- **Build another extension** — now that you know how, the sky's the limit. Ideas: a bookmark organizer, a tab manager, a website blocker for focus time, or a color picker tool

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "Manifest is not valid" | Make sure `manifest_version` is set to `3` (not 2). Check for missing commas or typos in JSON. |
| Popup is blank/white | Right-click the popup → Inspect → Console. Look for JavaScript errors. |
| Notes aren't saving | Make sure `storage` is listed in the `permissions` array in `manifest.json` |
| Context menu not showing | Check that `contextMenus` is in permissions and `background.js` is registered as a service worker |
| Extension disappeared after Chrome update | Unpacked extensions sometimes get disabled. Just re-enable it at `chrome://extensions/` |
| Chrome Web Store rejection | Most common reason: insufficient privacy policy or requesting unnecessary permissions. Keep permissions minimal. |
