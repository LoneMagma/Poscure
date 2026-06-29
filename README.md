<div align="center">

<br>

<img src="https://raw.githubusercontent.com/lonemagma/poscure/main/assets/icon.png" width="88" alt="Poscure logo" />

<h1>Poscure</h1>

<p><em>Draw more. Think less.</em></p>

<p>
A minimalist desktop app for gesture drawing and figure study.<br>
Load your references, set a timer, start drawing — nothing else in the way.
</p>

<br>

[![License: MIT](https://img.shields.io/badge/License-MIT-C8A97E.svg?style=flat-square&labelColor=16161A)](LICENSE)
[![Release](https://img.shields.io/badge/Release-v1.0.0-5A9E6F.svg?style=flat-square&labelColor=16161A)](https://github.com/lonemagma/poscure/releases/tag/v1.0.0)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-9896A4.svg?style=flat-square&labelColor=16161A)](https://github.com/lonemagma/poscure/releases)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3572A5.svg?style=flat-square&labelColor=16161A)](https://www.python.org/)
[![PySide6](https://img.shields.io/badge/PySide6-Qt6-41CD52.svg?style=flat-square&labelColor=16161A)](https://pypi.org/project/PySide6/)
[![Offline](https://img.shields.io/badge/100%25-Offline-C8A97E.svg?style=flat-square&labelColor=16161A)](#)
[![No Telemetry](https://img.shields.io/badge/No-Telemetry-B85C5C.svg?style=flat-square&labelColor=16161A)](#)
[![Pacify](https://img.shields.io/badge/Pacify-Project-C8A97E.svg?style=flat-square&labelColor=16161A)](https://pacify.site)

<br>

[**⬇ Download for Windows**](https://github.com/lonemagma/poscure/releases/download/v1.0.0/Poscure.exe) &nbsp;·&nbsp;
[**🌐 Live Site**](https://poscure.vercel.app) &nbsp;·&nbsp;
[**🐛 Report Issue**](https://github.com/lonemagma/poscure/issues)

<br>

</div>

---

## Overview

Poscure is a **local-first desktop practice tool** for artists who do gesture drawing and figure study. The idea is simple: you shouldn't have to think about the app. Point it at a folder, pick a timer, and draw.

Most alternatives are either web-based (which means your reference library lives online, loads slowly, or requires an account), or desktop apps that are bloated with features that interrupt the act of drawing. Poscure does one thing — run timed sessions over your own image library — and gets out of your way.

Everything runs offline. Your files never leave your machine. There are no accounts, no telemetry, no cloud sync, no monetization. It's a tool that needed to exist.

---

## Features

### 📁 Local Library Management

- Add unlimited local folders — Poscure scans them **recursively**
- Filter images by orientation (portrait / landscape / square)
- Drag a folder straight onto the sidebar to add it instantly
- SQLite-backed **thumbnail cache** so even 10,000+ image libraries feel snappy
- Background preloading — the next image is ready before the timer runs out

### ⏱ Timed Sessions

- **Fixed duration** — every image gets the same timer (e.g. 30 seconds)
- **Random duration** — varies within a range you set
- Built-in **break system** — configurable rest intervals between images
- Session presets for common workflows:

| Preset | Duration | Use case |
|--------|----------|----------|
| Quick Gesture | 30s | Loose, fast line warmup |
| Short Gesture | 60s | Build line economy and confidence |
| Figure Study | 2–5 min | Proportion, structure, weight |
| Long Study | 5–10 min | Anatomy, construction, detail |
| Custom | Any | You define it |

### 🖥 Fullscreen Session Mode

The session view is deliberately minimal. No panels, no menus — just the image and the timer.

```
╔══════════════════════════════════════════════╗
║  34 / 120  ● RUNNING          Figure Studies ║  ← HUD fades out after 3s
╠══════════════════════════════════════════════╣
║                                              ║
║                  [ image ]              ◷ 22 ║  ← ring timer, top-right
║                                              ║
╠══════════════════════════════════════════════╣
║ ████████████░░░░░░░░░░░░  28%               ║  ← session progress
║ ◀ Prev  ⏸ Pause  Next ▶  ⇆ Mirror  ◑ Gray ║  ← controls fade on idle
╚══════════════════════════════════════════════╝
```

Controls auto-hide after **3 seconds** of inactivity and return on any mouse movement. The ring timer depletes visually as each image's countdown runs. Previous image history is maintained even in random shuffle mode.

### 🔁 Live Transforms

Toggle mid-session without interrupting flow:

- **Mirror** — flip the image horizontally to catch asymmetry in your drawing
- **Grayscale** — strip colour to focus on value, form, and light

Both work in real time on whichever image is currently displayed.

### ⌨ Hotkey Reference

Every action in Poscure has a keyboard shortcut. The goal is to never need to touch the mouse during a session.

| Key | Action |
|-----|--------|
| `Space` | Pause / Resume |
| `→` / `N` | Next image |
| `←` / `P` | Previous image |
| `M` | Toggle mirror |
| `G` | Toggle grayscale |
| `T` | Adjust timer |
| `F` | Toggle fullscreen |
| `Esc` | End session |

> All shortcuts are **remappable** from the settings panel.

---

## Install

### Windows — portable `.exe`

No installer. No Python. Download and run.

**1. Download**

```
https://github.com/lonemagma/poscure/releases/download/v1.0.0/Poscure.exe
```

Size: ~58 MB · Source: github.com/lonemagma/poscure

**2. Run**

Double-click `Poscure.exe`. Windows may show a SmartScreen warning:

> **"Windows protected your PC"**

Click **"More info"** → **"Run anyway"**.

> **Why does this appear?** Code signing certificates cost ~$300/year. Poscure is unsigned but fully open source — you can read every line before running it. If you'd prefer, build from source instead (see the Linux instructions, they work on Windows too with Python installed).

**3. Add your image library**

Click **`+ Add`** in the sidebar, or drag any folder directly onto it. Poscure scans recursively and builds a thumbnail cache automatically.

---

### Linux — from source

**Prerequisites:** Python 3.10+, pip, git

```bash
# Clone the repo
git clone https://github.com/lonemagma/poscure
cd poscure

# ⚠ Known setup quirk: remove a ghost directory created by the repo
# This only needs to be done once, immediately after cloning
rm -rf src/{core,ui,widgets,utils}

# Create a virtual environment and install dependencies
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Launch
cd src && python main.py
```

> **The ghost directory step is not optional.** It's a known issue with how the repo was set up. If you skip it, imports will silently resolve to the wrong path and the app will fail to start.

---

### System Requirements

| | Windows | Linux |
|--|---------|-------|
| **OS** | Windows 10+ | Any modern distro |
| **Python** | Not required (portable exe) | 3.10+ |
| **Dependencies** | Bundled | PySide6, Pillow (via pip) |
| **Disk space** | ~58 MB + cache | ~100 MB + cache |
| **macOS** | — | Works from source (untested in v1) |

---

## Project Structure

```
poscure/
├── src/
│   ├── main.py              Entry point
│   ├── core/
│   │   ├── session.py       Session state machine, image queue, timer logic
│   │   ├── library.py       Folder management, recursive scanning
│   │   └── cache.py         SQLite thumbnail cache
│   ├── ui/
│   │   ├── main_window.py   Root window and layout
│   │   ├── library_view.py  Sidebar + image grid
│   │   └── session_view.py  Fullscreen session mode
│   ├── widgets/             Reusable components (ring timer, image cell, etc.)
│   └── utils/
│       ├── transforms.py    Mirror, grayscale, resize logic (Pillow)
│       └── config.py        Settings persistence
├── requirements.txt
└── LICENSE
```

---

## Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Language | Python 3.10+ | Core runtime |
| GUI | PySide6 (Qt6) | Cross-platform desktop UI |
| Images | Pillow | Loading, transforms, thumbnail generation |
| Storage | SQLite | Thumbnail cache, session state, folder registry |

No web views. No Electron. No 300 MB `node_modules`. Native Qt6 widgets, rendered by the OS.

---

## Roadmap

Things that may land in a future version:

- [ ] macOS `.app` build (v1 works from source but untested)
- [ ] Session history and stats (images seen, total time drawn)
- [ ] Export session as a playlist / re-run a past session
- [ ] Custom session presets that persist between runs
- [ ] Linux `.AppImage` or Flatpak release

PRs and issue reports are welcome.

---

## Contributing

1. **Fork** the repo and clone your fork
2. Create a branch: `git checkout -b feature/what-youre-adding`
3. Make your changes — keep diffs focused
4. Open a PR with a clear description of what changed and why

Please open an issue before starting significant work. It avoids duplicate effort and helps make sure the direction fits.

---

## AI Disclosure

Most of Poscure's codebase was written by **Claude (Anthropic)**, directed through sessions on Claude.ai. This is intentional and not something being hidden — one person using AI as a force multiplier can ship what normally takes a small team, without compromising on structure or intent.

Architecture decisions, UX choices, feature scope, and everything shipped are entirely human. An architect doesn't lay every brick; the building is still theirs.

**Tools used:**
- [Claude (Anthropic)](https://claude.ai) — code generation, debugging
- Python · PySide6 · Pillow · SQLite — runtime stack

---

## License

MIT — do whatever you want with it. See [`LICENSE`](LICENSE).

---

<div align="center">

<br>

Made with ♥ by [LoneMagma](https://instagram.com/lonemagma) &nbsp;·&nbsp; Part of [Pacify](https://pacify.site)

<br>

</div>
