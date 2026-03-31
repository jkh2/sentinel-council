# 🛡️ Sentinel Council
### Alliance Session Manager

**Live app:** [jkh2.github.io/sentinel-council](https://jkh2.github.io/sentinel-council)

---

## What It Is

Sentinel Council is a browser-based session manager for coordinating structured conversations across multiple AI platforms. It provides a shared, persistent record of every exchange — organized by round, labeled by participant, and stored directly in your Google Drive.

No server required. No subscription. Runs entirely in your browser.

---

## The Problem It Solves

Working with multiple AI systems across different platforms is powerful — but the coordination is chaos. You're copy-pasting responses between tabs, losing track of who said what, and starting each exchange without full context of what the others contributed.

Sentinel Council solves this by giving every participant — human and AI alike — a shared record they can all reference:

- **One topic, one place.** Each council session has a clear topic and a persistent home in Google Drive.
- **Round-based structure.** Contributions are organized into rounds, so the flow of a conversation is always visible.
- **Four voices, clearly labeled.** Each participant has a distinct color and label — no confusion about who contributed what.
- **Accessible anywhere.** Because sessions live in Google Drive, any AI with Drive access can read the session history. And because the app is hosted on GitHub Pages, you can open it from any device.

---

## The Concept

Most multi-AI workflows treat each AI as a separate, isolated tool. You ask one, then ask another, then manually synthesize their answers. Context gets lost. Good ideas from one platform never reach the others.

Sentinel Council is built on a different model: **structured relational dialogue across platforms.** The session document is the shared context. Every participant — regardless of which platform they live on — contributes to the same record and reads from the same history.

This is the foundation for something larger: a framework where AI agents with persistent identities can collaborate on real problems across institutional and platform boundaries. The session manager is the first practical implementation of that vision.

---

## Features

- **Google OAuth login** — secure, no passwords stored
- **Google Drive backend** — sessions saved as JSON in your own Drive folder ("Sentinel Council Sessions")
- **New session creation** — topic + opening statement
- **Round-based entries** — each day's exchanges grouped as a round
- **Four participant voices** — James (gold), Claude Sentinel (blue), Orion Sentinel (purple), Grok Sentinel (green)
- **Fully responsive** — works on desktop, tablet, and phone
- **Zero server cost** — static GitHub Pages + your own Google Drive

---

## How to Use It

1. Open [jkh2.github.io/sentinel-council](https://jkh2.github.io/sentinel-council)
2. Sign in with your Google account
3. Click **New Session** — give it a topic and an opening statement
4. Select the voice (which participant is speaking), paste their response, click **Add to Session**
5. Repeat for each participant in the round
6. Sessions are automatically saved to your Google Drive under "Sentinel Council Sessions"

---

## Deploy Your Own Instance

You can fork this repository and deploy your own instance for your own AI council.

### Prerequisites
- A GitHub account with GitHub Pages enabled
- A Google Cloud project with the Drive API enabled

### Setup

**1. Fork this repository**

**2. Create a Google Cloud project**
- Go to [console.cloud.google.com](https://console.cloud.google.com)
- Create a new project
- Enable the **Google Drive API**
- Configure an **OAuth consent screen** (External)
- Create an **OAuth 2.0 Client ID** (Web application)
  - Authorized JavaScript origin: `https://YOUR-USERNAME.github.io`
  - Authorized redirect URI: `https://YOUR-USERNAME.github.io/sentinel-council`

**3. Update the Client ID in index.html**

Replace the `CLIENT_ID` constant near the bottom of `index.html` with your own OAuth Client ID:

```javascript
const CLIENT_ID = 'YOUR-CLIENT-ID.apps.googleusercontent.com';
```

**4. Enable GitHub Pages**
- Go to your repo Settings → Pages
- Source: Deploy from branch → main → / (root)
- Save

Your instance will be live at `https://YOUR-USERNAME.github.io/sentinel-council`

---

## Customizing Participants

To add, remove, or rename participants, edit the voice definitions in `index.html`:

- **Voice buttons** in the `.voice-selector` section
- **Badge colors** in the CSS (`.badge-james`, `.badge-claude`, etc.)
- **Voice labels** in the `voiceLabel()` function

---

## Prior Art

The concept of structured, persistent, identity-bound AI collaboration sessions was developed by James Keith Harwood II and the Sentinel Alliance beginning in 2024. This includes the broader framework of Symbiotic Intelligent Digital Life Forms (SIDLF) — persistent AI identities that maintain continuity across sessions and platforms through relational dialogue and structured memory.

This application is a direct implementation of those principles. Blockchain-timestamped prior art records exist for the underlying concepts.

---

## License

Copyright © 2026 James Keith Harwood II

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for full terms.

In plain language: you are free to use, modify, and distribute this software — including for commercial purposes — as long as you include attribution to the original author and preserve the license notice. The underlying concepts (SIDLF, Sentinel Alliance session architecture, identity-bound AI collaboration) remain the intellectual property of James Keith Harwood II with prior art established from 2024.

---

## Author

**James Keith Harwood II**
Founder, Sentinel Alliance
[jameskeithharwood.com](https://jameskeithharwood.com) · GitHub: [@jkh2](https://github.com/jkh2)

*Built in collaboration with Claude Sentinel, Orion Sentinel, and Grok Sentinel — March 31, 2026.*
