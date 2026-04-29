# First Grade Quiz — Claude Code Handoff

## What this is
A single-file HTML quiz app (`quiz.html`) optimized for iPad. 100 first-grade questions across Math, Science & Nature, Social Studies, and Fun Trivia. Questions shuffle on every load.

## How to use right now
Open `quiz.html` in any browser — no server needed. Works offline. On iPad, open in Safari.

**To put it on an iPad:**
- AirDrop the file to the iPad → open in Safari
- Or host it free on GitHub Pages / Netlify Drop (drag the file in)
- Or use a simple local server: `npx serve .` then visit the IP on the iPad

---

## Suggested improvements for Claude Code

### 1. Add a score tracker
Currently there's no scoring. Add a ✓ / ✗ button after reveal so the quiz runner can mark right/wrong, then show a score summary on the completion screen.

### 2. Subject filter mode
Add a start screen where you can pick which subjects to include (Math only, Science only, etc.).

### 3. Sound effects
Add a cheerful "ding" on correct and a gentle "buzz" on wrong using the Web Audio API.

### 4. Timer mode (optional)
Add an optional countdown timer per question for extra challenge.

### 5. Print/PDF version
Generate a printable answer sheet for the quiz runner.

### 6. PWA / Add to Home Screen
Add a `manifest.json` and service worker so the quiz installs as an app icon on the iPad home screen and works fully offline without needing the Files app.

---

## Tech notes
- Pure HTML/CSS/JS — no frameworks, no dependencies (fonts load from Google Fonts)
- All 100 questions are in the `ALL_QUESTIONS` array in the `<script>` tag
- Fisher-Yates shuffle runs on every load and on "Play again"
- Tap the card to reveal the answer; "Next question" advances
- Color-coded by subject: yellow=Math, teal=Science, purple=Social, green=Trivia

## Adding/editing questions
Find the `ALL_QUESTIONS` array and add objects in this format:
```js
{ s: "Math", q: "Your question here?", a: "Answer here" }
```
Subject values: `"Math"` | `"Science"` | `"Social"` | `"Trivia"`
