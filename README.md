# terminal-itda

Your computer's AI at work, live in your pocket.

terminal-itda lets you follow and steer Claude Code and Codex on your computer from your phone. Start a task at your desk, walk away, and pick it up on the phone: read the replies, answer its questions, send the next instruction. You get a notification when the work is done.

It has two parts: a phone app, and a small program you install on your computer. This repository has the computer program. The source code is not public.

**Phone app:** Android and iPhone coming soon<br>
**Website:** coming soon<br>
**Contact:** [customer@newer.co.kr](mailto:customer@newer.co.kr)

## What you can do from the phone

- See what each AI is working on, on every computer you connect
- Read the conversation and reply in a chat view, or open the real terminal
- Get a notification when a task finishes or needs your answer; it goes away once you've looked
- Answer the AI's questions (run this command? which option?) with a tap: the choices show on the phone
- Send photos, screenshots or clipboard images for the AI to look at
- Tap a file the AI mentions (`docs/PLAN.md:12`) to read it from the computer
- See how much of your Claude and Codex plan is left, and when it resets
- Keep a laptop awake, even with the lid closed, and see its battery and heat (Pro)

The chat view works with Claude Code and Codex. Any other command-line tool (Gemini CLI, aider, and so on) works in the terminal view.

If you already use herdr, Orca or cmux, their agents show up in the app too, so you keep working in the tools you use now. What each one is doing comes from the tool itself, so the AIs it knows (OpenCode, Gemini, Grok, Hermes, OpenClaw, Codebuff, Command Code and many more) show as working, waiting for you, or done.

## Get started

**1. Install the app on your phone.** (Coming soon)

**2. Install terminal-itda on your computer.** Open a terminal and paste one line.

macOS or Linux:

```sh
curl -fsSL https://github.com/da-itda/terminal-itda/releases/latest/download/install.sh | sh
```

Windows (PowerShell):

```powershell
irm https://github.com/da-itda/terminal-itda/releases/latest/download/install.ps1 | iex
```

The installer asks before it changes anything. It sets terminal-itda to start when you log in and, at the end, shows a QR code.

**3. Scan the QR code with the app.** Approve the phone on the computer, and the computer appears in the app.

To connect another phone later, run `terminal-itda pair`.

On macOS and Windows, terminal-itda also has an icon in the menu bar (macOS) or the notification area (Windows). Its menu shows the connected phones, work in progress and the computer's IP addresses (click one to copy it). From the same menu you can turn keep awake on or off, connect a smartphone, check for updates and install them, and quit terminal-itda.

## Requirements

- macOS, Linux with systemd (Ubuntu, Debian, Fedora, …), or Windows 10 (1809) or later
- Claude Code or Codex, installed and signed in on the computer
- The computer needs to be on and awake while you use it from the phone

At home the phone connects to the computer over Wi-Fi. Elsewhere it goes through our relay server. Either way the connection is end-to-end encrypted between your phone and your computer, and the relay can't read it.

If Windows Firewall asks about terminal-itda, allow it so phones on the same Wi-Fi can connect directly.

## Commands

`itda` is a short alias for `terminal-itda`.

| Command | What it does |
|---|---|
| `terminal-itda status` | What is running and which phones are connected |
| `terminal-itda pair` | Connect a phone |
| `terminal-itda devices` | List connected phones (`devices remove <n>` to remove one) |
| `terminal-itda tools` | herdr, Orca and cmux: which ones the app uses (`tools off orca`) |
| `terminal-itda ssh` | Set up SSH from your phone through Tailscale (optional) |
| `terminal-itda awake setup` | macOS: let it stay awake with the lid closed (asks for your password once) |
| `terminal-itda update` | Update to the latest version |
| `terminal-itda service restart` | Restart the background service |
| `terminal-itda uninstall` | Stop the service and undo setup |

## Privacy

- Your conversations stay on your computer. The app reads them from the computer when you open them; they aren't uploaded anywhere.
- Your Claude and Codex logins never leave the computer. For plan usage, only the percentages and reset times go to your phone.
- Images you send are saved on the computer in `~/.itda/uploads` and deleted after 7 days.
- Notifications are encrypted on the computer and only your phone can read them.

## Pricing

terminal-itda is free with one computer. Pro connects more computers and keeps a laptop awake with the lid closed. Prices will be on the website.
The AI tools themselves (Claude, Codex) are billed by their own providers.

## Help

Questions, problems or ideas: [customer@newer.co.kr](mailto:customer@newer.co.kr)

When something doesn't work, `terminal-itda status` usually shows why. Include its output in your email.

---

© Newer. terminal-itda is not open source. See [LICENSE](LICENSE).
