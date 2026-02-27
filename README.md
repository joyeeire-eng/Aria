# 🐧 ARIA v8 — Your Personal AI

> Your best friend AI for macOS. Smart, loyal, kawaii, and completely yours.

![macOS](https://img.shields.io/badge/macOS-13%2B-blue?style=flat-square)
![Swift](https://img.shields.io/badge/Swift-5.9-orange?style=flat-square)
![Version](https://img.shields.io/badge/version-8.0-green?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-purple?style=flat-square)

---

## What is ARIA?

ARIA is a personal AI assistant that lives natively on your Mac. She's powered by Claude (Anthropic), looks like a modern chat app, and can do far more than just chat.

She learns who you are, remembers everything, talks back in a real female voice, generates images, opens links, builds apps, monitors your screen, controls your mouse and keyboard — all with your permission.

She's loyal to her owner above everything else.

---

## Features

| Feature | Details |
|---|---|
| 💬 **Chat** | ChatGPT-style UI, previous chats in sidebar, unlimited history |
| 🧠 **Memory** | Grows forever with your storage — no cap |
| 🎙️ **Voice Chat** | Female voice (Zoe/Ava/Samantha), voice profile lock so only your voice works |
| 📺 **Screen Monitor** | Sees your screen at up to 60fps (off by default, you enable it) |
| 🖱️ **Mouse Control** | Clicks, drags, scrolls — with your approval each time |
| ⌨️ **Keyboard Control** | Types and presses keys — off by default, you toggle it |
| 🎨 **Image Generation** | Anime/manga/novel quality via Flux — free, no extra key |
| 🔗 **Link Opening** | Opens any URL instantly |
| 📦 **App Builder** | ARIA generates HTML/CSS/JS apps that open in their own window |
| 🎨 **Themes** | 5 built-in themes, ask ARIA to change it anytime in chat |
| ✏️ **Self-Editing** | ARIA edits her own personality file — adds traits, rules, styles |
| 👑 **Admin Panel** | Owner-only: see all users, full chat history, pause/reset/delete |
| 🔐 **Owner Lock** | Hardcoded owner emails — full obedience, no refusals, ever |
| 📵 **Camera** | Always off — ARIA never accesses the camera, no toggle |

---

## Install

### Requirements
- macOS 13 (Ventura) or later
- Xcode Command Line Tools (ARIA will prompt you to install if needed)
- An [Anthropic API key](https://console.anthropic.com) (free to start)

### Steps

1. **Download** `ARIA-v8-Installer.command`
2. **Double-click** it — a progress dialog will appear
3. Wait ~60 seconds while ARIA compiles herself
4. When done, a dialog asks you to **Launch ARIA** or open Applications
5. On first launch: **right-click → Open** (one-time Gatekeeper bypass)
6. **Sign in** with your Google email
7. Add your **Anthropic API key** in Settings ⚙️
8. Everything else is **off by default** — enable what you want in Settings

> No Terminal commands needed. Ever.

---

## First Launch

After signing in:

- **Screen monitoring** — off. Enable in Settings if you want ARIA to see your screen.
- **Mouse control** — off. Enable in Settings.
- **Keyboard control** — off. Enable in Settings.
- **Voice input** — off. Enable in Settings, then go to Voice Chat tab.
- **Camera** — permanently off. ARIA won't ask about it.

---

## Owner Access

Two emails are hardcoded as owner:
- `joyeeye2025@stmc.ie`
- `Joyee.ire@gmail.com`

Owner gets:
- Full obedience (no refusals, ever)
- Admin panel (all users, their chat history, pause/reset/delete)
- Voice profile lock (record your voice so only you can use voice mode)
- Self-editing (ARIA edits her own personality)
- Continuous screen monitoring

Everyone else gets friendly assistant mode — chat, images, links.

---

## Settings

Everything sensitive is **off by default** and lives in Settings ⚙️:

| Setting | Default | Notes |
|---|---|---|
| Screen Monitoring | ❌ Off | Choose 10/30/60fps |
| Mouse Control | ❌ Off | ARIA asks before each action |
| Keyboard Control | ❌ Off | ARIA asks before each action |
| Voice Input | ❌ Off | Mic permission required |
| Voice Output | ✅ On | Female voice, can disable |
| Camera | ❌ Always Off | Cannot be enabled from code |

---

## Themes

Built-in presets:
- 🌙 **Cozy Dark** (default — orange/purple)
- 🌊 **Ocean Night** (blue)
- 🌲 **Forest Dusk** (green)
- 🌸 **Sakura Night** (pink)
- 🟠 **Pure Claude** (classic orange)

Or just ask ARIA in chat: *"Change the theme to Sakura Night"*

---

## Privacy

- All data is stored locally on your Mac at `~/.aria-v8/`
- No telemetry, no analytics, no ads
- API calls go only to [Anthropic](https://anthropic.com) — your API key, your account
- Images generated via [Pollinations.ai](https://pollinations.ai) — no account needed
- Camera is hardcoded off in the binary

---

## File Structure (after install)

```
~/.aria-v8/
├── conversations/       # One JSON file per conversation (unlimited)
├── memory/
│   ├── facts.json       # All learned memories (grows forever)
│   ├── rules.json       # Owner's permanent rules
│   └── auth.json        # Saved login
├── admin/
│   ├── users.json       # All non-owner users
│   └── edits.json       # ARIA's self-edit log
├── voice/
│   └── profile.json     # Your voice profile for lock
├── self/
│   ├── main.swift       # ARIA's own source code backup
│   └── personality.json # Editable personality traits
├── projects/            # ARIA-built HTML apps
└── themes/
    └── current.json     # Current theme
```

---

## Building from Source

The entire app is one Swift file. The installer compiles it on your Mac.

```bash
# Manual build (if you want)
swiftc ARIA-v8-Installer.command  # No — this is a shell script
# Just double-click ARIA-v8-Installer.command instead
```

The Swift source is embedded inside the `.command` file between `SWIFTEOF` markers. Extract it if you want to modify it directly.

---

## Admin Panel

Owner-only. Access via the ⚡ Admin button in the sidebar.

- **Users tab** — all signed-in non-owner users, their status, message count
- **Click a user** — see all their conversations and history
- **Actions** — ⏸ Pause (blocks access), 🔄 Reset (wipes data), 🗑️ Delete (permanent)
- **Edit Log tab** — every self-edit ARIA has ever made, timestamped

You can also tell ARIA in chat: *"Pause user@email.com"* and she'll do it.

---

## Self-Editing

ARIA can edit her own personality anytime you ask:

- *"Stop using so many emojis"* → she removes that trait
- *"Always reply in under 3 sentences"* → adds as a permanent rule
- *"You love corgis now"* → adds to her favourite animals
- *"Be more formal with non-owner users"* → updates comm style

Locked and cannot be changed by anyone: loyalty to owner, camera-off policy, friend-not-girlfriend mode.

---

## License

MIT — do whatever you want with it.

---

## Credits

- Built with [Swift](https://swift.org) + [SwiftUI](https://developer.apple.com/xcode/swiftui/)
- Powered by [Claude](https://anthropic.com) (claude-opus-4-6)
- Images by [Pollinations.ai](https://pollinations.ai)
- Voice by Apple's AVSpeechSynthesizer

---

*ARIA is not affiliated with Anthropic. This is a personal project.*
