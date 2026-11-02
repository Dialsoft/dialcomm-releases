# DialComm Terminal – Release Notes

DialComm is a BBS terminal for Windows and Android, published by **Dialsoft LLC** (Marc Frega, Wharton, NJ) and developed with Claude, the AI from Anthropic.
The Windows and Android versions share one terminal engine, so their version numbers run side by side (Windows 1.7.0 = Android 1.9.0).

---

## Windows 1.7.2 – November 2, 2026

**New**
- **Skip Tour.** The welcome tour that opens when DialComm starts now has a clear Skip Tour button on every page. Tick "Don't show this at startup" too and it won't open by itself again (Help → Welcome Tour still shows it).

## Windows 1.7.1 – November 1, 2026

**New**
- **Fast-starting installer.** DialComm for Windows now comes as an installer, DialComm-1.7.1-Setup.exe. It installs into your own user folder (no administrator rights needed), adds Start menu and desktop shortcuts, and opens DialComm in a second or two instead of about 20 seconds. Check for Updates installs new versions the same way, all by itself.
- **Portable copy still offered.** DialComm-1.7.1-Portable.exe needs no installing and runs from anywhere, such as a USB stick. It still takes 15–20 seconds to open, because it unpacks the whole program each time it starts. A portable copy keeps updating itself as a portable copy.
- **Smaller.** Only the English language files of the built-in browser engine are included, which saves about 50 MB on disk.

**Fixed**
- Slow start: the old portable-only download unpacked about 360 MB to a temporary folder, and Windows Defender scanned it, every time DialComm opened.

## Windows 1.7.0 / Android 1.9.0 – November 1, 2026

**New**
- **Ribbon (Windows).** A modern ribbon replaces the menu bar and Action Bar: Home, Transfer, View, Scripts, Options and Help tabs with large, labelled buttons, plus a File button. Emulation, screen size and font can be changed straight from the View tab. Ctrl+F1 (or ▴) hides the buttons for more screen room, and Alt plus a tab's letter opens it.
- **Classic look kept.** Setup → Window → Look switches between the ribbon and the classic Procomm Plus menus and Action Bar. The change happens instantly.
- **Check for Updates.** Help → Check for Updates (Windows) or Settings → Check for updates (Android). On Windows it downloads the new version beside the old one and starts it, and your directory and settings carry over. On Android it downloads the new app to install. DialComm also checks by itself once a day (you can turn that off), and a version can be skipped.
- **Tell a Friend.** Sends someone a note with the download link. On Windows you can choose email, Gmail, Outlook.com, Facebook Messenger, a Facebook post, WhatsApp, Telegram, X, Reddit, Discord or a text message, and the message can be edited first. On Android it opens the phone's own share menu.
- **Release Notes** (this document) are now inside the app: Help → Release Notes.
- **Code documentation:** every source file was given full internal comments: a summary at the top of each file, the purpose of each section and function, and the reasons behind tricky code. About a quarter of all lines are now comments, up from about 7%. A check proved the program itself was not changed.

**Fixed**
- Rapid Connect's first BBS: choosing the first BBS in the list did nothing, because it was already showing. The box now starts on "Pick a BBS to call…", so every BBS calls.
- Tab clicks: the tab strip no longer rebuilds itself while a busy BBS is sending, so a click on a tab always lands.

## Windows 1.6.0 / Android 1.8.0 – November 1, 2026
- **Tabs: several BBSes at once.** Each BBS gets its own tab, like a web browser. Each tab keeps its own screen, scrollback, fonts, capture file, script and file transfers, and background tabs keep running.
- A bold tab means new text and ♪ means the BBS rang the bell. Middle-click or × closes a tab, and right-click gives more options.
- Keys: Ctrl+Tab and Ctrl+Shift+Tab move between tabs; Ctrl+Shift+T and Ctrl+Shift+W open and close them. A Zmodem download starting in a background tab brings that tab forward.
- Setup → Window → Tabs: open a new tab, ask, or hang up and reuse the tab.
- Android: tap the BBS name at the top to switch between the BBSes you're on.

## Windows 1.5.0 / Android 1.7.0 – October 31, 2026
SyncTERM-class terminal features:
- **Fonts:** 46 classic PC, Amiga and other fonts (from VileR's Oldschool PC Font Pack), BBS-selected font slots and fonts uploaded by the BBS, and character sets (CP437, CP850, CP866, KOI8-R, ISO-8859-1 and more).
- **Pictures** inside the text: sixel, PPM/PBM and JPEG XL. They scroll with the text and go into the scrollback.
- **Modem-speed playback** (300–115,200 baud) so ANSI animations play as they were made.
- **Mouse reporting** for BBSes that use the mouse, bracketed paste, rectangle operations, macros and a host status line.
- **More ways to connect:** RLogin automatic logon, WebSocket gateways, and IEMSI automatic logon.
- **More emulations:** BBC Micro Mode 7 and Atari ST (VT52).

## Windows 1.4.4 / Android 1.6.5 – October 29, 2026
- First-in, first-out scrollback of 1,000 screens by default, adjustable up to 10,000, with a page indicator while you scroll back.

## Windows 1.4.3 / Android 1.6.4 – October 28, 2026
- Web and e-mail links on the BBS screen are recognised and can be clicked (Ctrl+click when the BBS uses the mouse).

## Windows 1.4.2 / Android 1.6.3 – October 26, 2026
- Welcome tour at start-up, with a "Don't show this at startup" checkbox.

## Windows 1.4.0–1.4.1 / Android 1.6.0–1.6.2 – October 25, 2026
- 256-colour and true-colour ANSI, and SyncTERM-compatible BBS sound effects.
- Windows: full Dialsoft LLC copyright, version and credits in the program's file properties.
- Android: scripts page, floating buttons beside the screen, a Google Play (AAB) build, and the view no longer jumps during ANSI animations.

## Android 1.0–1.5 – October 25, 2026
- First Android version: touch interface with a searchable BBS list, telnet connections that stay up while the app is in the background, RIPscrip, pinch zoom, full screen when sideways, scrollback by dragging down, app icon, About and credits.

## Windows 1.0–1.3.1 – October 2026
- The first DialComm releases: a recreation of Procomm Plus for Windows 4.8 for BBS use.
- Telnet, SSH and modem connections; ANSI-BBS, VT100/VT220, Avatar, Doorway, PETSCII, ATASCII and Viewdata emulations; RIPscrip graphics.
- Zmodem, Ymodem and Xmodem transfers; Procomm Plus ASPECT scripts with a script editor; Meta Keys; and a Connection Directory pre-loaded with BBSes.

---

## How DialComm is made

### Development software

| Part | What it is built with |
|---|---|
| Programming languages | **JavaScript** (Node.js / ECMAScript 2022) for the terminal engine and screens; **HTML5** and **CSS3** for the windows and controls; **Java** for the Android parts that talk to the phone (network sockets, background service, sharing, downloads) |
| Windows program | **Electron 45** (the Chromium browser engine with Node.js), packaged by **electron-builder 26** as an installer (NSIS) and as a no-install portable .exe. **resedit** writes the Dialsoft LLC version, copyright and credit details into the .exe |
| Android app | **Capacitor 7** (runs the shared engine inside Android's WebView), the **Android SDK** (API level 35, works on Android 8.0 / API 26 and newer), **Gradle**, **Java 21**. **esbuild** bundles the shared engine for the phone |
| Shared engine | The same source files run on both: screen emulation, fonts, RIPscrip, file transfers, scripting, the directory and settings. Small "shims" stand in for Windows-only pieces on Android |
| Libraries | **ssh2** (SSH connections), **serialport** (real modems), **zmodem.js** (Zmodem protocol), **libjxl** compiled to WebAssembly (JPEG XL pictures), VileR's **Oldschool PC Font Pack** (fonts, CC BY-SA 4.0) |
| Source control and builds | **Git**, with a private **GitHub** repository (Dialsoft/dialcomm). **GitHub Actions** builds and signs the Android app (APK and Google Play AAB) automatically on every change. The Windows .exe is built with electron-builder |
| Testing | Automated walk-throughs that drive the real program with keyboard and mouse events and screenshots (Electron under a virtual display for Windows; **Playwright** with a simulated phone for Android). Local test BBS servers cover ANSI, CTerm, animation, links and RIPscrip |
| Development | Written with **Claude** (Anthropic's AI), directed and tested by Marc Frega / Dialsoft LLC |

### Standards and protocols DialComm follows

**Terminal emulation**
- **ECMA-48 / ANSI X3.64** control sequences, as used by **ANSI-BBS** (the PC BBS dialect with CP437 line drawing, iCE colours and ANSI music)
- **CTerm / SyncTERM** extensions (SyncTERM's cterm specification): font slots and loadable fonts, speed emulation (DECSCS), status line, macros, rectangle operations, device attribute replies
- **DEC VT100 / VT220** and **VT52** (Atari ST)
- **xterm** colours (256-colour and 24-bit true colour), **mouse reporting** (modes 9, 1000, 1002, 1003, 1006 and 1016), **bracketed paste** (2004), **OSC 8** hyperlinks, OSC 4/10/11/104 palette changes and window titles
- **DEC Sixel** graphics; SyncTERM picture commands carrying **Netpbm** (PPM/PBM) and **JPEG XL** (ISO/IEC 18181) images
- **RIPscrip 1.54** vector graphics, buttons and mouse fields
- **Avatar (AVT/0)**, **Doorway** mode, **PETSCII** (Commodore 64), **ATASCII** (Atari 8-bit), **Viewdata / Prestel**, **BBC Micro Mode 7 (teletext)**
- Character sets: **IBM code pages** 437, 850, 865 and 866, **Windows-1251**, **KOI8-R / KOI8-U**, **ISO-8859** parts 1, 2, 4, 5, 7, 8, 9 and 15, and **UTF-8**

**Connections**
- **Telnet** (RFC 854) with option negotiation: binary transmission (RFC 856), echo (RFC 857), suppress go-ahead (RFC 858), terminal type (RFC 1091), and window size / NAWS (RFC 1073); linemode (RFC 1184) is politely declined, as BBSes expect character-at-a-time
- **SSH-2** (RFC 4251–4254), **RLogin** (RFC 1282), **WebSocket** (RFC 6455) gateways carrying telnet
- **RS-232 serial** modems with the **Hayes AT** command set
- **IEMSI** automatic logon (FidoNet FSC-0056)

**File transfers**
- **Zmodem** (Chuck Forsberg, 1988), **Ymodem** and Ymodem-batch, **Xmodem**, Xmodem-CRC and Xmodem-1K

**Scripting**
- Procomm Plus **ASPECT** script language (.WAS source), compatible with Procomm Plus for Windows scripts

### Coding standards
- **One engine, two platforms.** Windows and Android run the same terminal source, so a fix or feature reaches both.
- **Settings take effect immediately.** Nothing ever needs a restart or reload.
- **Plain-language help everywhere.** Every button, box and setting has a detailed tooltip, and messages say what to do next.
- **Safety.** Links from a BBS can only open web pages, never programs or files. Updates only download from the official DialComm download page. Passwords in the Connection Directory are encrypted with Windows' own data protection.
- **Comments in the code.** Each file starts with a summary of what it does. Each part is introduced by a comment explaining its purpose and how it fits with the rest, and tricky lines say *why*, not just *what*. Comment-only changes are checked automatically to prove the program itself did not change.
- **Strict JavaScript** (`'use strict'`) throughout, small single-purpose modules, and no hidden network activity: the only things DialComm contacts on its own are the BBSes you call and, once a day if allowed, the update check.
- **Tested before release** with the automated walk-throughs above on both platforms.

---

Copyright © 2026 Dialsoft LLC – Marc Frega, Wharton, NJ. All rights reserved.
