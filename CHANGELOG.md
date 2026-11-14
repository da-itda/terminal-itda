# Changelog

What changed in terminal-itda for your computer, and why. Each version is also on the [releases page](https://github.com/da-itda/terminal-itda/releases).

## 0.21.4 (2026-11-14)

**A new tray panel on Windows, and update checks that stay open.**

#### Why
- Clicking "Check for updates" closed the menu (macOS panel, Windows menu), so the result could only be seen by opening it again
- The Windows menu was Windows' plain menu, unlike the macOS panel

#### What's changed
- The update button shows its check, the result and the update where it was pressed; the panel closes when you click elsewhere or press Esc
- Windows: the notification-area icon opens a panel like the macOS one: the computer and its addresses (click to copy), connect a phone, your AI work with status badges, this computer (phones, SSH, keep awake switch), local models, and the version with update and quit
- The Windows panel follows the system's light or dark mode, has rounded corners on Windows 11 and stays sharp at any display scale
- The Windows panel shows 5 AI works; the rest are counted below
- Test builds no longer offer the release before them as an update

## 0.21.3 (2026-11-14)

**Windows updates are no longer stopped by Microsoft Defender.**

#### Why
- On Windows, updating from the menu, the notice or `terminal-itda update` could stop without a word: Microsoft Defender took the update command (the installer downloaded and run in one go) for malware (Trojan:Win32/Commando.B!ml) and ended it, so the old version stayed

#### What's changed
- `terminal-itda update` downloads the installer, checks it against the release's checksums, saves it and runs the file; a changed installer is never run
- The same on macOS and Linux
- If an update from 0.21.2 or older is stopped on Windows, try again, or run the install command in a PowerShell window

## 0.21.2 (2026-11-13)

**The update notice is the system's own notification.**

#### Why
- The update notice was a box in the middle of the screen, not the notification other programs show at the side
- A new version could wait up to 6 hours before the computer heard of it
- An update run in a terminal restarted terminal-itda twice

#### What's changed
- The update notice comes in at the side of the screen and stays in the notification list, under terminal-itda's name and icon (macOS Notification Center, Windows notifications)
- Click it and terminal-itda updates in a terminal right away, then restarts
- macOS asks once whether terminal-itda may send notifications; turn them off or on again in System Settings › Notifications › terminal-itda
- New versions are checked every hour
- An update from the menu or the notice restarts terminal-itda once

## 0.21.1 (2026-11-13)

**Work comes back in the mode you left it in, and an update popup.**

#### Why
- Claude opened in bypass came back in auto after a restart, and Codex in yolo came back asking for approvals: only the conversation was continued, so each program started in its settings' default
- After a forced power-off, a Codex could come back in another pane, or not at all
- On Windows, a remote herdr reconnecting after a restart could start herdr's server with administrator rights
- An update was only seen by those who looked for it

#### What's changed
- Work comes back in the mode you chose: Claude's permission mode (bypass, plan, auto, …) and Codex's approvals and sandbox (yolo, …), read from the conversation's own log and launch command
- Every AI in herdr is remembered with its place (workspace, tab, pane), conversation and mode; after a restart each one is checked, and one that came back in the wrong pane or mode is opened again as it was, only while nobody can have used it
- herdr 0.9.5 or later is told the whole command for each pane, so it opens them in their mode right away; with an older herdr server terminal-itda does it after herdr starts
- Codex comes back without its update question; a Codex conversation whose log Codex compressed is still continued
- A conversation whose folder was renamed comes back in its current mode
- AIs in plain terminals (tmux, iTerm2, Terminal, Windows consoles) and cmux open again once after a restart, in their folder and mode
- Windows: herdr's server starts with ordinary rights the moment you log on, and the logon task brings work back before terminal-itda itself is up
- `terminal-itda tools repair on|off` turns the automatic repair after a restart on or off (on)
- A popup says when terminal-itda has an update, once per version; `terminal-itda update` takes the newest release listed on GitHub

## 0.21.0 (2026-11-12)

**Claude and Codex in plain terminals, and live progress in chat.**

#### Why
- Claude Code or Codex started in a plain terminal (no herdr, Orca or cmux) only showed as a past conversation
- While the AI worked, the chat only said "working", not what it was doing
- The same conversation resumed in two places by hand splits its history
- After a computer went down without warning (a restart that hung, a power cut), work in herdr didn't open again

#### What's changed
- Claude Code and Codex in plain terminals show in a new **Terminal** tab, with their status
- tmux: full control from the phone (read the screen, type, keys)
- iTerm2: read the screen and send messages
- macOS Terminal and others: **Type from the phone too** moves the conversation into terminal-itda, in the same Terminal tab
- Windows: AIs started from a shell are found too; the desktop apps are left out
- The chat shows the AI's live status line and the tool it runs right now
- **Open twice:** the app marks a conversation open in two places, says where the other one is, and takes you there
- Work opens again even after the computer goes down without warning: settings and the list of open work are saved so a power cut can't empty them
- Windows: `file://C:/…` links open
- The **Terminal** tab, the live status line and **Open twice** show in the phone app from its next update (1.1.0)

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
