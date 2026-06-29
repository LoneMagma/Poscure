<div align="center">

<br>

<svg xmlns="http://www.w3.org/2000/svg" width="72" height="72" viewBox="0 0 72 72" fill="none">
  <rect width="72" height="72" rx="18" fill="#16161A"/>
  <rect width="72" height="72" rx="18" stroke="#2C2C36" stroke-width="1.5"/>
  <ellipse cx="36" cy="22" rx="7.5" ry="8.5" fill="none" stroke="#C8A97E" stroke-width="2.5"/>
  <path d="M36 30.5 L36 47" stroke="#C8A97E" stroke-width="2.5" stroke-linecap="round"/>
  <path d="M36 36 L27 43" stroke="#C8A97E" stroke-width="2.2" stroke-linecap="round"/>
  <path d="M36 36 L45 43" stroke="#C8A97E" stroke-width="2.2" stroke-linecap="round"/>
  <path d="M36 47 L29 60" stroke="#C8A97E" stroke-width="2.2" stroke-linecap="round"/>
  <path d="M36 47 L43 60" stroke="#C8A97E" stroke-width="2.2" stroke-linecap="round"/>
</svg>

<h1>Poscure</h1>

<p><strong>Draw more. Think less.</strong></p>

<p>A minimalist desktop app for gesture drawing and figure study.<br>Load your references, set a timer, and practice without friction.</p>

<br>

[![License: MIT](https://img.shields.io/badge/License-MIT-C8A97E?style=flat-square&labelColor=16161A)](https://github.com/lonemagma/poscure/blob/main/LICENSE)
[![Release](https://img.shields.io/badge/Release-v1.0.0-5A9E6F?style=flat-square&labelColor=16161A)](https://github.com/lonemagma/poscure/releases/tag/v1.0.0)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-9896A4?style=flat-square&labelColor=16161A)](https://github.com/lonemagma/poscure/releases)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3572A5?style=flat-square&labelColor=16161A)](https://www.python.org/)
[![Built with PySide6](https://img.shields.io/badge/PySide6-Qt6-41CD52?style=flat-square&labelColor=16161A)](https://pypi.org/project/PySide6/)
[![Pacify Project](https://img.shields.io/badge/Pacify-Project-C8A97E?style=flat-square&labelColor=16161A)](https://pacify.site)

<br>

**[Download for Windows](https://github.com/lonemagma/poscure/releases/download/v1.0.0/Poscure.exe)** · **[Live Site](https://poscure.vercel.app)** · **[Report an Issue](https://github.com/lonemagma/poscure/issues)**

<br>

</div>

---

## What is Poscure?

Poscure is a local-first, offline desktop tool for artists who practice gesture drawing and figure study. You give it a folder of reference images, set a timer duration, and it takes care of the rest — cycling through images, counting down, and staying completely out of your way.

There are no accounts, no internet connection required, no telemetry, and no cloud storage. Your files stay on your machine.

---

## Features

| | |
|---|---|
| **Your own library** | Unlimited local folders with recursive scanning and orientation filtering |
| **Timed sessions** | Fixed or random duration per image — 30s gestures up to 10min studies |
| **Fullscreen focus** | Session mode fills the screen; controls auto-hide after 3 seconds |
| **Live transforms** | Mirror and grayscale toggle mid-session, including in random mode |
| **Hotkey-driven** | Space pauses, arrows navigate, G/M toggle transforms — all remappable |
| **Smart caching** | SQLite thumbnail cache with background preloading; fast with 10k+ libraries |

---

## Install

### Windows

The Windows release is a single portable `.exe` — no installer, no Python required.

1. **[Download Poscure.exe](https://github.com/lonemagma/poscure/releases/download/v1.0.0/Poscure.exe)** (~58 MB)
2. Double-click to run. If Windows SmartScreen appears, click **"More info"** → **"Run anyway"**

> **Why the SmartScreen warning?** Code signing certificates cost ~$300/year. The app is unsigned but fully open source — read the source if you want to verify it before running.

3. Click **"+ Add Folder"** or drag a folder onto the sidebar to add your image library

---

### Linux

```bash
# 1. Clone and remove a known ghost directory (required once after clone)
git clone https://github.com/lonemagma/poscure
cd poscure
rm -rf src/{core,ui,widgets,utils}

# 2. Set up Python environment and install dependencies
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt

# 3. Run
cd src && python main.py
```

---

### Requirements

| Requirement | Notes |
|---|---|
| Windows 10+ or Linux | macOS works from source (untested in v1) |
| Python 3.10+ | Linux / source only — Windows .exe is self-contained |
| PySide6 + Pillow | Auto-installed via `pip install -r requirements.txt` |
| ~100 MB disk | App binary + SQLite thumbnail cache |

---

## Who it's for

- **Gesture drawers** — 30–60s sessions with rapid image cycling
- **Figure study artists** — longer sessions with structured breaks
- **Illustration students** — curated reference packs for specific subjects
- **Daily warmup artists** — opens fast, no friction, gets out of your way

---

## Tech Stack

```
Python 3.10+    Core runtime
PySide6         Qt6 GUI framework
Pillow          Image loading and transforms
SQLite          Thumbnail cache and session state
```

---

## Project Structure

```
poscure/
├── src/
│   ├── main.py          Entry point
│   ├── core/            Session logic, timer, image queue
│   ├── ui/              Main window, library view, session view
│   ├── widgets/         Reusable UI components
│   └── utils/           Image transforms, caching helpers
├── requirements.txt
└── LICENSE
```

---

## Contributing

Poscure is MIT licensed and issues/PRs are welcome.

1. Fork the repo
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit your changes
4. Open a pull request

Please open an issue before working on anything significant — it helps avoid duplicate effort.

---

## About

<table>
<tr>
<td><strong>Author</strong></td>
<td>LoneMagma — <a href="https://instagram.com/lonemagma">@lonemagma</a> · <a href="https://pacify.site">pacify.site</a></td>
</tr>
<tr>
<td><strong>Part of</strong></td>
<td><a href="https://pacify.site">Pacify</a> — a family of focused, zero-noise tools</td>
</tr>
<tr>
<td><strong>License</strong></td>
<td>MIT</td>
</tr>
</table>

### AI Disclosure

The majority of Poscure's codebase was generated by **Claude (Anthropic)** through directed sessions on Claude.ai. This is a deliberate choice — one developer using AI can ship what normally takes a team, without sacrificing structure or intent.

The architecture, UX decisions, and product direction are entirely human. An architect doesn't lay every brick; the building is still theirs.

---

<div align="center">

<br>

Made with ♥ by [LoneMagma](https://instagram.com/lonemagma) · Part of [Pacify](https://pacify.site)

<br>

</div>
