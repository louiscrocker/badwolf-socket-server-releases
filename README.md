<div align="center">

# 🐺 BADWOLF Socket Server

### *The other end of the wire.*

[![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011%20x64-0078D6?style=for-the-badge&logo=windows&logoColor=white)](../../releases/latest)
[![Free](https://img.shields.io/badge/Free%20to%20use-freeware-00FF41?style=for-the-badge)](LICENSE)
[![No telemetry](https://img.shields.io/badge/Telemetry-none-ff2e88?style=for-the-badge)](#-privacy)

<br />

**A scriptable TCP + UDP lab endpoint with a real-time cyberpunk dashboard.**
Bind a port, watch every client and byte, script replies, drive timed feeds, and record/replay whole sessions.

---

</div>

## 📥 Download

Get the latest version from **[Releases](../../releases/latest)**:

| File | What it is |
|---|---|
| `BADWOLF.Socket.Server_<version>_x64-setup.exe` | Installer, per-user, no admin rights needed (**recommended**) |
| `BADWOLF.Socket.Server_<version>_x64_en-US.msi` | MSI, per-machine, for managed installs |
| `SHA256SUMS.txt` | Checksums: verify with `Get-FileHash <file>` in PowerShell |
| `probe.py` | Optional tiny test client (Python 3, standard library only) |

### Before you install

- **Windows SmartScreen.** The installers aren't code-signed yet, so Windows may say *"Windows protected your PC"*. Check the SHA-256 against `SHA256SUMS.txt`, then choose **More info → Run anyway**.
- **WebView2.** Preinstalled on Windows 11. On Windows 10 the installer fetches it if it's missing.
- **Firewall.** The default bind is `127.0.0.1` (this machine only). If you bind `0.0.0.0`, Windows will ask before allowing network access.

## 🌐 Docs

**[Website and documentation →](https://louiscrocker.github.io/badwolf-socket-server-docs/)**

## ✨ Highlights

- ⚡ **TCP + UDP** listeners with newline, CRLF, u16 length-prefix or raw framing
- ⎌ **Live message stream** with TEXT and HEX views, direct send and instant KICK
- ⚙ **Auto-responder**: exact / prefix / contains / regex / hex-prefix rules → templated replies
- ≋ **Feeds**: timed broadcasts, plus a built-in GEO world-map marker stream
- ● **Record → export JSONL → replay** with the original timing
- 🎛 **Seven scenario presets**: echo, chat relay, IoT sensor, mock line-API, binary device, geo, auth-gated
- `--start` to begin listening at launch, for lab scripts and classrooms

## 🚀 Quick start

1. Install and launch. Open **CONFIG**, pick a scenario preset and press **LOAD**, then **START**.
2. Connect with `ncat 127.0.0.1 8888` (add `-u` for UDP), or `python probe.py` from the release.
3. Watch the stream, add **RULES**, record a session, KICK a client.

## 🔒 Privacy

The app makes **no outbound network connections**: no telemetry, no update check, no remote fonts.
It only listens on the address and port you configure.

## 🐞 Reporting a problem

Open an [issue](../../issues) with what you did and what happened. If the app or listener stopped
unexpectedly, attach `%LOCALAPPDATA%\com.badwolf.socket-server\logs\diagnostics.log`. It's
local-only and records lifecycle events and errors, never message contents.

## 📄 Licence

**Free to use, closed source.** See [LICENSE](LICENSE). You may use the app at no cost for any
lawful purpose, including commercial and classroom use, and share the unmodified installers. The
source code isn't published. Open-source components and fonts included in the app are listed with
their licences in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

---

<div align="center">

### Built with 🐺 by BADWOLF

**[Tauri](https://v2.tauri.app)** · **[Rust](https://www.rust-lang.org)** · **[Tokio](https://tokio.rs)**

</div>
