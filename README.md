# Wispling Releases

This is the public release channel for **Wispling**, a small creature that lives
on your desktop. It holds public release artifacts and installation guidance.
The source code is private and is not here.

## Availability

**The native 3D cat/dog release is not ready for public installation.**

Release metadata checked on **2026-09-17 (UTC)**:

| Release | Status |
|---|---|
| Stable `latest`: [`v0.1.0`](https://github.com/saketlunker/wispling-releases/releases/tag/v0.1.0) | Legacy EXE/MSI installers and checksums. No native `install.ps1` or `wispling-update.json` asset. |
| Legacy beta: [`v0.1.1-beta.7`](https://github.com/saketlunker/wispling-releases/releases/tag/v0.1.1-beta.7) | A prerelease of the older delivery path, not the native cat/dog candidate. |
| Planned native candidate: `v0.2.0-beta.1` | Not published. No approved native installation is available from this tag yet. |
| `pipeline-test-*` | Prerelease test payloads, not the Wispling application. |

The repository-root `install.ps1` and the manifests under `releases\` belong to
legacy clients. They are retained for compatibility, **not recommended as a
native installation path**. Their presence does not mean the native release is
available.

### Native beta opt-in: not available yet

A native beta must be chosen by its exact approved release tag. Only after
`v0.2.0-beta.1` is approved and published with the real native application would
its one-line installation be:

```powershell
irm https://github.com/saketlunker/wispling-releases/releases/download/v0.2.0-beta.1/install.ps1 | iex
```

**This is a future, tag-specific command, not a working download today.** Do not
substitute a `pipeline-test-*` tag. The approved beta installer must keep its
manifest URL pinned to that same beta tag.

Choosing a beta must not repoint `latest`, the default root installer, or the
stable manifests to a beta. Beta update activation also remains subject to
candidate approval; opting in does not silently join a moving update channel.

### Native stable installation: unavailable

The native stable one-line command will be documented after an approved native
stable release exists. The current `latest` release has no native installer
asset. Neither `latest/download/install.ps1` nor the raw repository-root script
is a native stable installation route today.

## The upcoming native app

The native release is an original 3D cat/dog companion built in Rust for
64-bit Windows. It requires no Node.js, npm, browser, or GPU acceleration. Core pet
behavior works offline, with no telemetry or screen capture.

Optional conversation requires a separately running **GitHubRelay** reached
through the local machine's loopback interface. If that relay is unavailable,
conversation must report that honestly; it must not pretend to work. The core
offline pet must remain usable.

These describe the native release, not the legacy downloads listed above.

## Native delivery contract: not released yet

Native release approval requires the behavior below. This is not a claim that
the legacy installers implement it.

### Installation and updates

Installation is per-user, with no administrator requirement and no PATH change:

```text
%LOCALAPPDATA%\Wispling\app     the program
%LOCALAPPDATA%\Wispling\data    your pet's memories
```

Nothing is installed for other users or into Program Files. Signed automatic
updates verify the native manifest and payloads before activating a replacement
application folder. Activation must be atomic, with rollback and recovery after
an interrupted swap. Memories remain outside the replaced folder and must not
be rewritten by an update.

The native manifest uses Ed25519 key
`wispling-update-ed25519-066bb2fb07a0bdad`. The installer and updater must verify
the signed manifest and the listed artifact hashes. A checksum alone is not a
publisher signature.

### Removing the native app

After an approved native installation, use **Add or Remove Programs**, or the
`uninstall.ps1` asset from that installation's exact release tag. Do not use
`latest` to choose an uninstaller for a beta.

Removal must clean up the program, shortcut, registration, and updater, then
report exactly what remains. **Your pet's memories are kept by default** in
`%LOCALAPPDATA%\Wispling\data`. Deleting them requires a separate, explicit
choice. Reinstalling must not overwrite retained memories.

### Windows security warnings

**Wispling does not have a Windows code-signing certificate.** A signed native
update manifest is not a Windows publisher identity and does not remove Windows
warnings.

If Windows warns or blocks installation, stop. The native installer must not
disable protections, change script-execution policy, remove download security
markings, or install a trust certificate to get past a warning.

## Expected native release assets

These are the native delivery format, not a list of currently available
downloads:

| File | Purpose |
|---|---|
| `install.ps1` | Tag-pinned one-line installer |
| `uninstall.ps1` | Data-preserving uninstaller |
| `wispling-update.json` | Signed native manifest |
| `wispling_<version>_windows-x64.zip` | Native application payload |
| `wispling-update-helper.exe` | Native update helper |

Only approved public release artifacts belong here. No core source, authoring
tools, model GLBs, private documentation, development binaries, or credentials.
Legacy manifests and release assets are retained for existing clients; they
must not be silently migrated to the native format.

## Credits

Wispling began as a rebrand of [`jupram/tokki`](https://github.com/jupram/tokki) by
Jupram, used under the MIT license and with permission. That history is credited
here; the upcoming native Rust cat/dog app is an original implementation.
