# Wispling

**A real 3D companion, living on your Windows desktop.**

Not a sprite, not a looping animation. A model you can take hold of and turn with
your mouse on all three axes, rendered entirely on the CPU by one small native
binary. No GPU, no browser engine, nothing else to install.

This is the 3D beta. The creature it ships with is Pebble, a small blue wind-up
toy that walks about, naps, stretches and yawns, jumps and swirls, and offers a
joke then waits for you to ask for the punchline. Pebble is the first companion
here, not the last. The 3D is the product.

## Install

One line, once. Paste it into PowerShell:

```powershell
irm https://github.com/saketlunker/wispling-releases/releases/latest/download/install.ps1 | iex
```

That installs Wispling for your Windows account and starts it. No administrator
rights, no second step, and nothing to run again afterwards.

## Pebble

A round blue shell, a pale cream face, dark oval eyes and a small smile. Warm
cheeks, copper side plates, a copper ring on top and two short dark feet.

Drag it with the right mouse button and it turns on all three axes, because it is
a model rather than a picture of one. Drag with the left and you move it; leave it
somewhere and it stays there.

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

The 3D beta installs for your Windows account only. No administrator rights are
needed.

```text
%LOCALAPPDATA%\Wispling\app\   the application
%LOCALAPPDATA%\Wispling\data\  saved conversations and memories
```

**Wispling keeps itself current.** It looks for a new version quietly in the
background and applies it the next time it starts or closes, so you never run the
install line twice, and a companion is never interrupted to be updated.

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
