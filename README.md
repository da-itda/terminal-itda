# terminal-itda

Use your computer's terminal and AI coding tools (Claude Code, Codex) from your phone.
Install it on your computer, scan the QR code with the phone app, and you're connected.

## Install (one line in the terminal)

**macOS · Linux**
```sh
curl -fsSL https://github.com/da-itda/terminal-itda/releases/latest/download/install.sh | sh
```
Linux needs systemd for the background service (Ubuntu, Debian, Fedora, …).

**Windows** (PowerShell, Windows 10 1809 or later)
```powershell
irm https://github.com/da-itda/terminal-itda/releases/latest/download/install.ps1 | iex
```
If Windows Firewall asks about terminal-itda, allow it so phones on your Wi-Fi connect directly.

What the installer does
1. Installs terminal-itda (short alias: `itda`) for your OS and CPU, or updates it to the latest version.
2. Checks Claude Code, Codex and herdr. It asks before installing anything missing or updating anything out of date.
3. Sets up the background service and terminal integration, then shows a QR code to connect your phone.

## Update
```sh
terminal-itda update
```

This repository contains release files only.
