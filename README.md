# Wispling

**Meet Pebble. A small blue wind-up companion for your Windows desktop.**

It walks about, settles down for a nap, stretches and yawns. It jumps and swirls.
It has a sense of humour, too: it offers a joke, then waits for you to ask for the
punchline. A little company while you work, without watching what you do.

## Install

One line, once. Paste it into PowerShell:

```powershell
irm https://github.com/saketlunker/wispling-releases/releases/download/v0.2.0-beta.1/install.ps1 | iex
```

That installs Pebble for your Windows account and starts it. No administrator
rights, no second step.

The command is pinned to the `v0.2.0-beta.1` tag on purpose. Pebble is a
prerelease, and `releases/latest` still resolves to the legacy `v0.1.0` from
September 14, 2026, which is not Pebble. The legacy downloads and the installer
at the root of this repository do not install Pebble.

## A real 3D toy

Wispling has one companion: Pebble. A round blue shell, a pale cream face, dark
oval eyes and a small smile. Warm cheeks, copper side plates, a copper ring on top
and two short dark feet.

Turn it with your mouse on all three axes. This is real 3D, not a flat animation.
The rendering runs entirely on the CPU in one small native Windows binary.
No GPU required. No browser engine. No runtime to install.

## Alive offline. Text chat by choice.

Without a chat service, Pebble still moves, reacts, sleeps and has moods.
That part of its life works offline.

To chat, you need **GitHubRelay**, installed separately and running on
loopback at `http://127.0.0.1:4141/v1`. Wispling does not ship a model. If Pebble
cannot reach the gateway, it says so plainly instead of pretending to answer.

Chat requests go to your local gateway. That does not mean the model itself runs
locally.

## Company, not surveillance

Wispling never:

- Takes a screenshot or reads your screen.
- Listens to your microphone.
- Reads your clipboard or personal files.
- Registers a global hotkey.

**There is no telemetry of any kind.**

Saved conversations and memories are encrypted on your own disk with
**AES-256-GCM**. The key lives in **Windows Credential Manager**.

## Your installation, your memories

The Pebble beta installs for your Windows account only. No administrator rights
are needed.

```text
%LOCALAPPDATA%\Wispling\app\   the application
%LOCALAPPDATA%\Wispling\data\  saved conversations and memories
```

**This first beta does not update itself.** Moving to a newer release means
running the install line again. The release after this one updates on its own:
it checks for a new version in the background, and applies it the next time
Pebble starts or closes, so there is nothing to run and nothing to click.

Updates replace `app\`, never `data\`. Memories survive updates and are kept
even after uninstall. Removing the app does not erase your saved conversations.

## Know before you install

- **Windows 10 and 11 only.**
- **English only.**
- **No screen-reader or IME support.**

Wispling does not have a Windows code-signing certificate. **Windows SmartScreen
may warn on first run.** The publisher is unknown to Windows; that warning is
real, not a mistake.

Do not bypass Windows protections. If installation or launch is blocked, stop.
On a managed work machine, follow your organization's software policy and check
with your IT team rather than trying to get around the block.

## Credits

Wispling began as a rebrand of [jupram/tokki](https://github.com/jupram/tokki) by
Jupram, used with permission, and has since diverged a long way. Tokki's MIT notice
ships with every release. All Wispling artwork is original.
