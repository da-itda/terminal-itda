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

## AI workspace tools
If you use herdr, Orca or cmux, their agents show up in the phone app too (a tab per tool), with their conversations and input.
Tools found on the computer are on by default. Turn one off in the app (computer ⋮ > Tools) or on the computer:
```sh
terminal-itda tools            # what is installed and running
terminal-itda tools off orca   # or: on, start
```
cmux only lets other programs in when Settings > Automation allows automation.

## SSH from your phone (Tailscale)
If the computer is on Tailscale, the app offers to add it as an SSH host: Tailscale SSH where it runs (Linux, Homebrew macOS), else the computer's SSH server with the phone's key.
```sh
terminal-itda ssh    # what is set up, and set up what is missing
```
On Windows, keys of administrator accounts are approved on the computer with `terminal-itda ssh`.

## Update
```sh
terminal-itda update
```

This repository contains release files only.
