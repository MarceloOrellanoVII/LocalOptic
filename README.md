# LocalOptic

Local AI image viewer, organizer, and search — **free, fully local, no cloud**.

100% Private & Self-Contained:
Your photos stay exactly where they are on your hard drive.
LocalOptic stores all generated data (indexes, AI descriptions, metadata, and batch rules) locally in its own data/ directory.
All application state is locked behind a password-protected local account, which you can easily export or import whenever you want to move or back up your data.

---

## Features

- 🔍 **AI-Powered Search:** Search your local media library using natural language.
- ⚡ **Fast Local Indexing:** Fast thumbnail generation and metadata management without uploading data anywhere.
- 📂 **Non-Destructive Management:** Organizes photos without altering or moving your original raw files.
- 🔒 **100% Offline & Private:** Built to run entirely on your local machine using local hardware.

---

## Requirements

- **OS:** Windows 10 / 11 (64-bit)
- **Optional AI Model:** [Ollama](https://ollama.com/) running `qwen2.5vl:7b` (~5 GB) for deep photo analysis. *(Basic viewing, search, and organization work without it).*

---

## Quick Start

### Running the Standalone Application
- Double-click `LocalOptic.exe` to launch in a native desktop window (with automatic browser fallback).
- Run `LocalOptic.exe serve` from the CLI for headless/server-only mode.

### Running in Development Mode
1. Run `install.bat` to set up the environment interactively.
2. Launch via `localoptic.bat` (or `.venv\Scripts\python.exe -m localoptic serve --standalone`).

---

## Project Structure

```text
localoptic\            the application package (stdlib + 4 runtime deps)
  model\               the model-interface subpackage (Qwen2.5-VL via Ollama)
  storage\             the SQLite repository (WAL)
UI\                    the web UI (index.html, app.js, app.css, favicon)
model\Qwen2.5-VL-7B\   the BPE tokenizer asset (exact token counts)
sounds\                the notification sound asset
tests\                 the full test suite (unit + API + browser E2E)
LocalOptic.spec        the PyInstaller spec (excludes heavy unused libraries)
localoptic_entry.py    the PyInstaller entry point
requirements.txt       runtime dependencies (pillow, tokenizers, cryptography, pywebview)
requirements-dev.txt   + build/test dependencies (pyinstaller, pytest, playwright, ...)
pyproject.toml         canonical package definition (same deps, plus [dev] extra)
LocalOptic.exe         the prebuilt standalone app (Windows, no console window)
install.bat / .ps1     interactive installer (no silent installs)
setup-on-new-pc.bat   one-time setup guide for a fresh machine
localoptic.bat         dev-mode launcher (venv)
uninstall.bat          uninstaller (never touches your photo index without asking)
---
pip install pyinstaller
pyinstaller LocalOptic.spec --noconfirm --clean
---
**LocalOptic** is created and maintained by **Marcelo Horacio Orellano**.

This software is distributed free of charge under a Custom End-User License Agreement (EULA). You are free to download, use, and share the official releases for personal use. Commercial redistribution, reselling, or re-uploading modified binaries to paid marketplaces without permission is strictly prohibited. See the full [LICENSE.txt](./LICENSE.txt) for details.
```
Support the Project

LocalOptic is independent software developed and provided for free. If you find it useful and want to support ongoing development, consider donating via PayPal:

- 💳 **PayPal:** https://www.paypal.com/donate/?hosted_button_id=YHFEX4KPGJ9R2

Your support is greatly appreciated!
```
