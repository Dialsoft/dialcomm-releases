# DialComm Terminal

**A BBS terminal for Windows, Mac, Linux and Android, by Dialsoft LLC.**

DialComm calls the bulletin board systems still running today over the internet (Telnet, SSH, RLogin, WebSocket) or a real modem, and shows them the way they were meant to look.

- **ANSI accuracy you can measure:** tested against the entire 16colo.rs ANSI art archive (57,110 files), DialComm's ANSI Art Viewer draws **99.6%** of them pixel-for-pixel identical to the reference (99.8% of all characters), and its terminal screen 98.7%
- ANSI art with 256-colour and true colour, iCE colours and the classic PC fonts
- An ANSI Art Viewer for .ANS, .ICE, .BIN, .XB, .ADF, .IDF, .TND and more, with modem-speed playback
- RIPscrip graphics, PETSCII (Commodore 64), ATASCII (Atari), Viewdata, BBC Mode 7 and Atari ST
- Zmodem, Ymodem and Xmodem file transfers
- Tabs: be on several BBSes at the same time
- Telnet, Secure Telnet (TLS), SSH and RLogin; VT100/VT220, xterm, Linux console, SCO ANSI, Wyse and TeleVideo emulations
- Runs on Windows, Mac (Apple Silicon and Intel), Linux and Android
- SyncTERM-style extras: BBS fonts, pictures (sixel, PPM, JPEG XL), mouse, sound
- ANSI music, modem-speed playback for animations, a big scrollback
- Procomm Plus ASPECT scripts, Meta Keys and a Connection Directory
- A modern ribbon, or the classic Procomm Plus for Windows look

## Download

| | Version | File |
|---|---|---|
| **Windows** (10 and 11): installer, recommended | 1.9.4 | [DialComm-1.9.4-Setup.exe](https://github.com/Dialsoft/dialcomm-releases/releases/download/windows-1.9.4/DialComm-1.9.4-Setup.exe) |
| **Windows**: portable, no install (for USB sticks; slower to start) | 1.9.4 | [DialComm-1.9.4-Portable.exe](https://github.com/Dialsoft/dialcomm-releases/releases/download/windows-1.9.4/DialComm-1.9.4-Portable.exe) |
| **Mac** (macOS 12 or later; Apple Silicon and Intel) | 1.9.4 | [DialComm-1.9.4-Mac.dmg](https://github.com/Dialsoft/dialcomm-releases/releases/download/windows-1.9.4/DialComm-1.9.4-Mac.dmg) |
| **Linux** (64-bit PC): AppImage, runs on any Linux | 1.9.4 | [DialComm-1.9.4-Linux.AppImage](https://github.com/Dialsoft/dialcomm-releases/releases/download/windows-1.9.4/DialComm-1.9.4-Linux.AppImage) |
| **Linux**: .deb package for Ubuntu, Debian, Mint, Pop!_OS... | 1.9.4 | [DialComm-1.9.4-Linux-amd64.deb](https://github.com/Dialsoft/dialcomm-releases/releases/download/windows-1.9.4/DialComm-1.9.4-Linux-amd64.deb) |
| **Android** | 1.11.1 | [DialComm-1.11.1.apk](https://github.com/Dialsoft/dialcomm-releases/releases/download/android-1.11.1/DialComm-1.11.1.apk) |

**Windows:** download the **Setup** file and run it. It installs DialComm for you (no administrator rights needed), adds Start menu and desktop shortcuts, and opens it; after that DialComm starts in a second or two. The **portable** file needs no installing and runs from anywhere, such as a USB stick, but it unpacks itself each time, so it takes 15–20 seconds to open. Windows may warn that it doesn't recognise the program; click *More info* → *Run anyway*.

**Mac:** open the .dmg and drag DialComm onto the Applications folder. DialComm isn't signed by Apple yet, so the first time you open it macOS says it can't check it: click *Done* (or *OK*), then go to **System Settings → Privacy & Security**, scroll down and click **Open Anyway** next to DialComm, and confirm. You only do this once; updates DialComm downloads itself open straight away.

**Linux:** the **AppImage** is one file that runs on any 64-bit Linux: download it, make it runnable (right-click → Properties → Permissions → *Allow executing as program*, or `chmod +x DialComm-*.AppImage`) and double-click it. On Ubuntu, Debian, Mint and the like you can instead open the **.deb** to install DialComm with your software installer (or `sudo apt install ./DialComm-*.deb`); it then appears in your applications menu. To use a real modem or serial port, add yourself to the *dialout* group once: `sudo usermod -aG dialout $USER`, then log out and back in.

**Android:** open the .apk on your phone. Android asks you to allow installs from your browser the first time.

DialComm checks for new versions by itself (Help → Check for Updates).

**What's new, how DialComm is made and the standards it follows:** see the [Release Notes](RELEASE_NOTES.md).

---

Copyright © 2026 Dialsoft LLC – Marc Frega, Wharton, NJ. All rights reserved.
Developed with Claude, the AI from Anthropic. PC fonts from The Ultimate Oldschool PC Font Pack by VileR (int10h.org), CC BY-SA 4.0.
