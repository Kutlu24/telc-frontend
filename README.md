# telc-frontend — C1 Hörverstehen

A browser-based practice app for the **TELC C1 Hörverstehen** (listening comprehension) exam section. Pairs with [telc-backend](https://github.com/Kutlu24/telc-backend), which supplies exam content and handles login.

🇩🇪 German version: [README.de.md](README.de.md)

## What it does

1. Log in (against `telc-backend`).
2. Fetch an exam text and its questions for a chosen *Teil* (exam part) from the backend.
3. The browser's built-in `SpeechSynthesisUtterance` API reads the German text aloud, simulating the listening portion of the exam.
4. Answer matching, multiple-choice, and fill-in-the-blank questions based on what was read.

## Tech stack

Plain HTML and vanilla JavaScript — no framework, no build step. Uses the Web Speech API (`SpeechSynthesisUtterance`) for text-to-speech, built into modern browsers.

## Backend connection

The app currently calls a hardcoded backend URL:

```
https://telc-backend-yjs9.onrender.com
```

`questions.json` and `texts.json` in this repository are local sample data — they are **not** read by the running app, which fetches everything from the live backend instead. Keep that in mind if you edit them expecting a visible effect.

## Known gap

This frontend calls `/exams` and `/questions` on the backend, but the current `telc-backend` repository only implements `/register` and `/login`. See the [telc-backend README](https://github.com/Kutlu24/telc-backend#known-gap) for the same note from the other side.
