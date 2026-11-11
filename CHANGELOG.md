# Changelog

What changed in terminal-itda for your computer, and why. Each version is also on the [releases page](https://github.com/da-itda/terminal-itda/releases).

## 0.20.4 (2026-11-04)

**Windows: elevated herdr handled for you.**

#### Why
- herdr started as administrator on Windows couldn't be reached

#### What's changed
- terminal-itda hands an elevated herdr over by itself
- The notice says running the fix once is enough

## 0.20.3 (2026-11-04)

**No duplicate work.**

#### Why
- Work running in another tool could be opened again in herdr

#### What's changed
- Work running in another tool isn't reopened in herdr
- A conversation guessed from a folder is used only when its agent is alone there

## 0.20.2 (2026-10-31)

**Work stays open after a restart.**

#### Why
- A restart closed work in progress, and a new agent could show an older conversation

#### What's changed
- herdr panes and terminal-itda sessions cut off by a restart open again
- A new agent's chat shows its own conversation
- Windows: the tray menu matches the macOS panel

## 0.20.1 (2026-10-29)

**Windows herdr fix.**

#### Why
- herdr opened over SSH didn't show on phones

#### What's changed
- Windows: herdr's server starts first, so its agents show on phones

## 0.20.0 (2026-10-29)

**SSH between your computers.**

#### Why
- With several computers, setting up SSH between them by hand is tedious

#### What's changed
- Setup offers Tailscale step by step: install, start, log in
- Each computer gets its own key; your phone hands each computer the others on your Tailscale network
- The menu and `terminal-itda status` show which computers you can `ssh` to

## 0.19.0 (2026-10-28)

**Local models and Hermes.**

#### Why
- Local models and Hermes conversations were invisible from the phone

#### What's changed
- A Models tab: Ollama and LM Studio models, loaded and installed
- Hermes conversations (its desktop app's too) in the history, continued with `hermes --resume`
- herdr: agents herdr doesn't detect are found from what runs in the pane
- macOS menu bar: a card-style panel (computer, AI work, phones, keep awake, local models)

## 0.18.0 (2026-10-28)

**AI agents through ACP.**

#### Why
- Agents like Hermes, OpenCode and Goose speak the Agent Client Protocol

#### What's changed
- Start new work with ACP agents (Hermes, OpenCode, Goose, …) from the phone
- The chat tells you why a message wasn't accepted
- Windows: SSH server setup runs in a visible administrator window, with a firewall rule

## 0.17.2 (2026-10-25)

**Close Orca agents from the phone.**

#### Why
- Orca agents couldn't be closed from the phone

#### What's changed
- Orca's agents can be closed from the app too

## 0.17.1 (2026-10-25)

**Close agents from the phone.**

#### Why
- Finished agents piled up and had to be closed on the computer

#### What's changed
- Close a herdr or cmux agent's window from the app

## 0.17.0 (2026-10-25)

**Notifications on iPhone.**

#### Why
- Notifications reached only Android phones

#### What's changed
- Notifications reach iPhones, end-to-end encrypted
- herdr: a folder's own workspace and conversation are found correctly

## 0.16.1 (2026-10-24)

**Notification settings fix.**

#### Why
- Notification settings didn't stick in some cases

#### What's changed
- Settings stay as you set them

## 0.16.0 (2026-10-24)

**Smarter status for more AIs.**

#### Why
- Status was guessed from the screen and missed some agents

#### What's changed
- Orca's own agent states are used
- More AIs are recognized by name (OpenCode, Gemini, Grok, Hermes, …)
- Questions in terminal-itda's own sessions reach the phone

## 0.15.1 (2026-10-22)

**Orca notification fix.**

#### Why
- Typing or switching views in Orca sent false "done" notifications

#### What's changed
- Done notifications only when Claude or Codex really finish
- A numbered question counts as waiting for you

## 0.15.0 (2026-10-22)

**Menu bar and tray icon.**

#### Why
- You need a quick way to see and control terminal-itda on the computer itself

#### What's changed
- An icon in the macOS menu bar and the Windows notification area
- Shows connected phones, work in progress and the computer's IP addresses (click to copy)
- Turn keep awake on or off, connect a phone, check for updates and install them, quit
- Keep awake off with the lid closed: sleeps now, or once no AI is working

## 0.14.0 (2026-10-22)

**Keep awake and rename work.**

#### Why
- A laptop that sleeps stops the AI; long lists of work are hard to tell apart

#### What's changed
- Keep awake (Pro): the computer stays on, even with the lid closed; battery and heat are shown
- `terminal-itda awake setup` (macOS) allows staying awake with the lid closed
- Rename work from the app; names are kept on the computer
- Windows: restarting the service over SSH starts it on the desktop

## 0.13.2 (2026-10-18)

**Links in answers open.**

#### Why
- File paths and links in the AI's answers weren't usable from the phone

#### What's changed
- Web links open in the browser; file paths open the file from the computer
- Opening a chat clears its notification

## 0.13.1 (2026-10-18)

**Send images to the AI.**

#### Why
- Screenshots and photos often explain a problem faster than words

#### What's changed
- The computer accepts images from the phone for the AI to look at
- Images are kept in `~/.itda/uploads` for 7 days

## 0.13.0 (2026-10-17)

**Notifications, plan usage, and Pro.**

#### Why
- You want to know when the AI is done without watching the screen

#### What's changed
- A notification when a task finishes or needs your answer
- See how much of your Claude Code and Codex plan is left, and when it resets
- Pro: a 14-day trial; the free plan covers one computer
- herdr is now optional: without a tool, new work opens in terminal-itda's own session

## 0.12.1 (2026-10-13)

**herdr fixes.**

#### Why
- New work from the phone didn't open in herdr, and installing herdr needed Homebrew

#### What's changed
- New work opens in herdr with agent names it accepts
- The installer can install herdr without Homebrew

## 0.12.0 (2026-10-13)

**Busy computers stay reachable.**

#### Why
- A slow tool could make the computer look offline in the app

#### What's changed
- Each tool is checked once and the answer shared; a slow tool keeps its last list, marked slow
- `terminal-itda status` shows slow tools
- The browser client and its local web page are removed (the phone app replaces them)

## 0.11.3 (2026-10-13)

**Status fix.**

#### Why
- `terminal-itda status` said SSH went through Tailscale when only the SSH server was on

#### What's changed
- The SSH line now says how phones really reach the computer

## 0.11.2 (2026-10-13)

**Updates really run the new version.**

#### Why
- After an update, the old background program could keep running

#### What's changed
- `terminal-itda service restart` reloads the service and stops a stray copy
- herdr is started on the computer, not from the phone

## 0.11.1 (2026-10-13)

**Installer fix.**

#### Why
- With `curl | sh`, the installer's questions weren't asked on the terminal (on Windows, it waited unseen)

#### What's changed
- The installers now ask their questions on the terminal

## 0.11.0 (2026-10-13)

**Work continues where it already runs.**

#### Why
- Opening a conversation from the phone could start a second copy in another place

#### What's changed
- Continuing a conversation goes to the herdr, Orca or cmux pane that runs it
- New work from the phone opens inside your tool (herdr, Orca or cmux), with a default you choose
- `terminal-itda` without arguments shows help; `terminal-itda status` shows what runs
- The shell integration is gone: your terminal is left as it is

## 0.10.0 (2026-10-12)

**SSH from your phone through Tailscale.**

#### Why
- Sometimes you need a real shell on the computer, not just the AI

#### What's changed
- `terminal-itda ssh` sets up SSH over Tailscale
- Paired phones add their key automatically and lose it when removed
- On Windows, an administrator approves the keys once

## 0.9.0 (2026-10-12)

**Works with AI workspace tools: herdr, Orca and cmux.**

#### Why
- Many people already run their agents inside a workspace tool; the app should show those agents where they are

#### What's changed
- Orca: its terminals' agents show in the app, with status, chat and input
- cmux: its terminals' agents show in the app; its unread notifications count as "needs you"
- `terminal-itda tools` turns each tool on or off for the app
- Windows: no more console windows flashing while a phone watches
- Typing at a shell prompt no longer counts as the AI working

## 0.8.0 (2026-10-12)

**Windows support.**

#### Why
- Windows users couldn't use terminal-itda

#### What's changed
- Windows 10 (1809) or later, amd64 and arm64
- PowerShell one-line installer (`install.ps1`)
- Starts when you log in; phones on the same Wi-Fi connect directly

## 0.7.0 (2026-10-12)

**Linux support.**

#### Why
- terminal-itda ran only on macOS

#### What's changed
- Linux with systemd (Ubuntu, Debian, Fedora, …): runs as a user service
- The same one-line installer works on Linux (amd64 and arm64)

## 0.6.2 (2026-10-12)

**Fix for updating from 0.6.0.**

#### Why
- After the rename, an update could leave the background service pointing at the old command

#### What's changed
- The installer re-points the service to `terminal-itda` after an update

## 0.6.1 (2026-10-12)

**The command is now `terminal-itda`.**

#### Why
- A clearer, unique command name

#### What's changed
- The command is `terminal-itda`, with `itda` as a short alias
- All text on the computer side is now in English

## 0.6.0 (2026-10-12)

**First public release of terminal-itda for your computer.**

#### Why
- Follow and steer the AI coding agents on your computer from your phone

#### What's changed
- One-line installer for macOS (`install.sh`)
- Pair a phone with a QR code, approved on the computer; the connection is end-to-end encrypted
- Works on the same Wi-Fi directly, and from anywhere through our relay (which can't read your data)
- See past Claude Code and Codex conversations per folder, and continue them
- Live chat view and terminal view; the app spots when the AI asks you something
- herdr support: its agents show in the app, with chat and input
- `itda update` installs the latest version (the command became `terminal-itda` in 0.6.1)
