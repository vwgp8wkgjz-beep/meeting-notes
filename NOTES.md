# Notes (meeting notes)

One-page meeting notes board you install as an app. Built as a sibling of Hours (`../hours-log`): same setup, same look, different job.

Live at: https://vwgp8wkgjz-beep.github.io/meeting-notes/

## Install it on a computer

1. Open the link above in Chrome or Edge.
2. Chrome: click the install icon at the right end of the address bar. Edge: menu (three dots), then Apps, then "Install this site as an app."
3. It gets its own icon and window, and opens without internet after the first visit.

The repo is public (decided 2026-10-28: free GitHub Pages needs a public repo). It holds only the app's code. Notes never leave the browser, so they are not in the repo or on the site.

## What it does

- Three sections stacked top to bottom: **This week**, **Being dealt with**, **Out of scope**. Each is a bullet list, one line per note: number, words, tags. Notes always list in number order, lowest first; new notes go at the bottom of This week. (Changed 2026-10-28 from side-by-side columns of cards, at David's request.)
- Type a note in the box at the top of "This week" and press Enter. Each note gets a number that never changes, so "number 4" means the same thing every week.
- Drag a note to move it to another section. (Reordering inside a section was dropped on 2026-10-28 so numbers always read in order.) Click a note's words to edit them.
- Four tags you can switch on or off for each note: Small prompt, Big, David, Michael. Click the + at the end of a line to show the unused tags; they close when you click anywhere else. Click a tag that's on to remove it.
- **Meeting tabs.** Each meeting gets a tab with its date. "+ New meeting" (shown when the latest meeting isn't today) starts today's meeting with every note carried over. Older tabs are read-only, so they stay an honest record of each meeting.
- **Email this meeting** opens your mail app with a new email: subject "Meeting notes, <date>", the notes grouped by section with numbers and tags. The "Send to" list is remembered. "Copy text" is there for when the mail app doesn't open or the email is very long.

## Updating

Push to the `main` branch of `vwgp8wkgjz-beep/meeting-notes` on GitHub. Pages republishes in a minute or two. Installed apps pick up the new version the next time they open with internet. If you change the list of app files, bump `CACHE` in `sw.js`.

## How it works

- `index.html` is the whole app. No libraries.
- `manifest.webmanifest`, `icons/` and `sw.js` make it installable and let it open offline. `sw.js` is a copy of Hours' file with its own cache name.
- Notes are saved in the browser on that computer only (same as Hours). Clearing that site's browser data deletes them.
- Deleting a note removes it from today's meeting only. It stays in the past tabs.
- Icons are drawn by a one-off Python script (three columns of cards on teal, from the first side-by-side design); the PNGs are the source.

## Built

2026-10-28. Tested in headless Chrome: adding notes, tags, dragging between sections (including grabbing a note by its words), editing, reload keeps everything, email text and remembered "Send to" list, new meeting carries notes over with numbers kept, past meeting read-only, phone layout.

Not tested: dragging on a real phone or iPad. Touch drag in browsers is less dependable than mouse drag.

## Next, if wanted

- Filter the board by a tag (for example, only Michael's notes).
- Backup and restore.
