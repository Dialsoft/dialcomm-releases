# DialComm Terminal – Release Notes

DialComm is a BBS terminal for Windows and Android, published by **Dialsoft LLC** (Marc Frega, Wharton, NJ) and developed with Claude, the AI from Anthropic.
The Windows and Android versions share one terminal engine, so their version numbers run side by side (Windows 1.7.0 = Android 1.9.0).

---

## Windows, Mac and Linux 1.9.4 / Android 1.11.1 – November 13, 2026

**ANSI accuracy: 99.6% pixel-perfect**
DialComm was re-tested against the entire 16colo.rs ANSI art archive (57,110 comparable files, 1990 to today), compared pixel by pixel with the reference picture of each file:

| | Before (1.9.3) | Now |
|---|---|---|
| ANSI Art Viewer: files pixel-perfect | 96.7% | **99.6%** |
| ANSI Art Viewer: characters identical | 99.79% | **99.84%** |
| Terminal screen: files pixel-perfect | 96.0% | **98.7%** |
| Art from 2010 on (viewer) | 76.7% | **98.5%** |

What changed:
- **9-dot art** (art drawn for the VGA's 720-pixel text mode) is shown with the same character shapes that PabloDraw, ansilove and 16colo.rs use, in a 9-dot cell with line drawings joined across the gap. DialComm used IBM's hardware-redrawn shapes for 47 characters (■, m, w, f and others), which art tools never showed. Both are in Setup's font list: "IBM VGA 9x16 (as ANSI art viewers show it)" and "IBM VGA 9x16 (true VGA text mode)".
- **PabloDraw 24-bit colors** (ESC[1;r;g;bt) now give way to bold and blink the way PabloDraw writes its files, so "now bright white" after a 24-bit color comes out right (BBSes and the art viewer).
- **ANSI Art Viewer:** carriage returns and line erases are ignored and NUL and backspace are drawn as characters, as art viewers do; ANSI music codes in art files show as text, as in art viewers.
- What's left is mostly art the reference viewer itself draws wrong (256-color art, the "bright" color codes 90-97 and the iCE-color switch ESC[?33h, which DialComm draws correctly), plus a handful of 1990 files with unusual cursor tricks.

## Windows, Mac and Linux 1.9.3 – November 8, 2026

**New: DialComm for Linux**
- Two downloads for 64-bit Linux PCs: an **AppImage** (one file that runs on any Linux: make it runnable and double-click it) and a **.deb package** for Ubuntu, Debian, Mint, Pop!_OS and the like, which installs DialComm into your applications menu.
- The same program as on Windows and Mac: ribbon, tabs, Connection Directory, every emulation, file transfers, scripts, the ANSI Art Viewer, Quick Dial and updates.
- **Check for Updates** on Linux: the AppImage downloads the new AppImage beside itself and starts it in its place; the .deb version downloads the new .deb and opens it in your software installer.
- Real modems and serial ports work as on Windows; Linux needs you in the *dialout* group once (`sudo usermod -aG dialout $USER`, then log out and back in).
- Tested on Ubuntu 24.04: the AppImage runs and the .deb installs and starts, as an ordinary (non-administrator) user.

**ANSI accuracy, now on every platform:** DialComm's ANSI drawing was tested against the entire 16colo.rs ANSI art archive (57,110 comparable files from 1990 to today): 96.0% are drawn pixel-for-pixel identical to the reference and 99.43% of all characters exactly right, 99.8% in the ANSI Art Viewer. Windows, Mac, Linux and Android all use the same drawing engine.

## Windows and Mac 1.9.2 – November 8, 2026

**New: DialComm for Mac**
- DialComm now runs on Macs: one download (DialComm-1.9.2-Mac.dmg) that runs natively on both Apple Silicon (M1 and later) and Intel Macs, macOS 12 or later. Everything the Windows version does, the Mac version does: the same ribbon, tabs, Connection Directory, emulations, file transfers, scripts, ANSI Art Viewer and updates.
- A proper Mac menu bar: DialComm → About / Hide / Quit (⌘Q); File → New Tab (⌘T), Close Tab (⌘W), Quick Dial (⇧⌘Q), Connection Directory (⇧⌘D); Edit → Copy (⌘C copies the text selected on the screen), Paste (⌘V types the clipboard to the BBS), Select All. In text boxes these work on the text as usual. Every Ctrl+Shift shortcut also works as ⌘+Shift; plain Ctrl+letter still goes to the BBS, as a terminal should.
- **Check for Updates** on a Mac downloads the new disk image to your Downloads folder and opens it: drag DialComm onto Applications and choose Replace.
- Serial ports for real modems show their Mac names (/dev/cu.usbserial…).
- **First start:** DialComm isn't signed by Apple yet (that needs a paid Apple Developer membership), so the first time, macOS says it can't check it. Click *Done*, then open **System Settings → Privacy & Security**, scroll down, click **Open Anyway** next to DialComm and confirm. Only once.
- Built and checked on a Mac by the publishing process: both processor types are in the app, its (ad-hoc) signature checks out, and it starts and shows its window.

## Windows 1.9.1 – November 4, 2026

**New: Quick Dial**
- A **Quick Dial** button next to Connect on the ribbon's Home tab (also File → Quick Dial…, the toolbar in the classic look, and Ctrl+Shift+Q). Type an address, with the port after a colon if you like (bbs.example.com:2323), pick **Telnet, Secure Telnet, SSH or RLogin**, and press Enter: DialComm calls it straight away, without adding it to the Connection Directory first.
- The port follows the connection type (23, 992, 22, 513) unless you type your own; SSH and RLogin show user name and password boxes.
- The last 15 addresses are remembered in the drop-down, with their port and connection type.
- Tick **Save it in the Connection Directory** to keep it (in a "Quick Dial" folder, with its call history). An address already in your Directory uses that entry, logon details and all.
- Paste on the ribbon's Home tab is now a small button, so the Home tab still fits a 1024-pixel-wide window.

## Windows 1.9.0 / Android 1.11.0 – November 4, 2026

**New: ANSI Art Viewer (Windows)**
- **File → View ANSI Art…** (also on the ribbon's Home tab, Capture group, or drag a file onto the window) shows art files from your PC: ANSI (.ANS, .ICE), text (.ASC, .NFO, .DIZ), Avatar (.AVT), PCBoard (.PCB) and the other BBS colour codes (PCBoard @X, Wildcat @@, WWIV heart codes and |00 pipe codes), Binary (.BIN), XBin (.XB, with its own palette and font), Artworx (.ADF), iCE Draw (.IDF) and TundraDraw (.TND, 24-bit colour). All seven of ansilove's test pictures, one per format, come out pixel-for-pixel the same as ansilove draws them.
- Shows the SAUCE details: title, artist, group, date, font and comments.
- **◀ ▶** step through every art file in the same folder, for looking through a whole art pack.
- **Play** draws the file at the speed of a modem you pick (300 to 115,200 baud), so ANSI animations move the way they were made. Space plays and pauses.
- Zoom (fit to window, 1x, 2x, 3x), 8 or 9 dots per character, iCE colours on or off, and **Save as Picture** (PNG).
- In art-file mode the bell, form feed and vertical tab characters show as their pictures and Unix line endings are understood, as art viewers do. On the whole 16colo.rs archive (57,110 comparable files) this draws **96.7%** of files exactly pixel-perfect and **99.79%** of all characters identical to the reference. (A live BBS still gets these characters treated as commands, as it should.)

**New: recording a session with timing**
- Setup → Transfer Protocol → **Capture as: Recording with timing (.ttyrec)**. The capture remembers when each piece of the BBS's output arrived, and the ANSI Art Viewer plays it back exactly as it happened. ttyrec is a standard format other players read too.

**New emulations**
- **xterm (Linux / Unix)** and **Linux console**, for shell accounts: UTF-8, 256 and 24-bit colour, the **alternate screen** (vim, nano, mc and htop give you your screen back when they exit), xterm's keys including Ctrl/Shift/Alt with the arrows and function keys, Alt as Meta, and mouse reporting.
- **SCO ANSI**, with SCO's colour codes and keys.
- **Wyse 50, Wyse 60, TeleVideo 925 and TeleVideo 950**, the "ASCII" terminals of old Unix, Xenix, PICK and accounting systems: their cursor, editing, attribute and line-graphics codes, and the keys they send.

**Improved: VT100 / VT220**
- Checked against **vttest**, the standard VT test program (cursor movement, screen features, double-size characters, terminal reports, VT52 mode, VT102 insert/delete), and fixed what it found:
  - real **underlining**; **double-width and double-height lines**; **reverse screen** (DECSCNM); **80/132 column switching** (DECCOLM) clears the screen as a real VT does and resizes the screen for that call
  - **VT52 mode** inside VT100 (ESC [ ? 2 l)
  - control characters inside an escape sequence are carried out, as on a real VT
  - cursor position reports in origin mode, new-line mode (Enter sends CR LF), the "terminal parameters" report (DECREQTPARM), and the number pad's application mode
  - the **printer port**: what the host prints (CSI 5 i ... CSI 4 i, print screen, print line) is saved to a text file in your Capture folder

**New: Secure Telnet (TelnetS)**
- Connection Directory → Advanced Options → Connect using → **Secure Telnet (TLS)**, usually port 992, on Windows and Android. BBSes nearly always make their own certificates, so DialComm remembers each BBS's certificate the first time and warns you if it ever changes (as with SSH keys). The status line says when a call is encrypted.

**New: Directory thumbnails (Windows)**
- Entry Info in the Connection Directory shows a small picture of the BBS's screen from the end of your last call, so you can recognise your BBSes at a glance. It's updated every call.

## Windows 1.8.4 / Android 1.10.2 – November 3, 2026

**New: address book folders and colour-coded hosts**
- **Folders.** The Connection Directory now has a Folders column. Make folders of your own (New, Rename, Delete, or right-click), and file BBSes in them by dragging them onto a folder, with the new Folder box in Entry Info, or from the right-click menu. Pick All entries, a folder, or Not in a folder to see just those BBSes; the numbers show how many are in each. Deleting a folder never deletes its BBSes. Find also searches folder names.
- **Colour labels.** Give any BBS one of ten colours (the swatches in Entry Info, or right-click). The colour shows as a dot in the Directory, in Rapid Connect, and as a bar along the top of the BBS's tab.
- **Rapid Connect follows your folders:** BBSes not in a folder first, then a heading for each folder, in the order you arranged them.
- BBSes added from the Telnet BBS Guide go into a *Telnet BBS Guide* folder.
- **Android:** the BBS list is grouped by folder (tap a folder's heading to fold it away) with a coloured stripe for each colour label; Edit BBS has Folder and Colour label, and ⋮ has Move to a folder and Colour label. Folders and colours are the same ones as on Windows.

**Fixed**
- Modem-speed pacing: text that arrives in the same block as a speed change (CSI Ps1 ; Ps2 * r) is now shown at the new speed straight away, instead of at the old one.

## Windows 1.8.3 / Android 1.10.1 – November 3, 2026

**Improved: ANSI art accuracy, tested against 500 real ANSIs from 16colo.rs**
- **How it was tested:** a new test bench draws 500 randomly chosen ANSI art files from every era with DialComm's own screen engine and compares every character with the reference pictures on 16colo.rs (drawn by ansilove, the art scene's standard). DialComm 1.8.2 drew 53.5% of them exactly right; this version draws **77.3%** exactly right, and **93.8%** of all characters match (99.6% for VGA 9-pixel art).
- **Column 80:** when a line fills the last column, the cursor now moves to the next line straight away, as DOS ANSI.SYS, the BBS terminals of the day and SyncTERM do (SyncTERM's own specification says so). Before, DialComm waited for the next character, as VT100 terminals do, which scrambled art that skips the line break after a full line. Setup → Terminal Options has a switch for the VT100 way, and BBSes can ask for it with SyncTERM's CSI = 4 h / CSI = 5 h.
- **Picture characters:** the bytes NUL, SO, SI, XON, XOFF and DEL now show their code page 437 pictures (blank, ♫, ☼, ◄, ‼, ⌂) instead of nothing, as DOS showed them, so art that uses them no longer drifts sideways. A NUL right after a carriage return (telnet's line-end padding) is still ignored.

## Windows 1.8.2 – November 3, 2026

**New**
- **Version on the status line.** Next to "Ready" at the bottom of the window, DialComm shows its version. When a newer one is out, the box turns yellow and says "Update available", and clicking it shows what's new and installs it. DialComm looks for a new version when it starts and every 6 hours (only when checking for updates is on in Setup → Window).

## Windows 1.8.1 – November 3, 2026

**Fixed**
- Rapid Connect alignment: the Rapid Connect box and the Telnet BBS Guide button under it now line up exactly, with the same width and height.

## Windows 1.8.0 / Android 1.10.0 – November 3, 2026

**New**
- **Telnet BBS Guide.** Over a thousand BBSes to call, from the monthly list published by The BBS Corner at telnetbbsguide.com. On Windows it's under Rapid Connect on the ribbon's Home tab (and File → Telnet BBS Guide). Search by name, BBS software or place, then Call one or Add it to your Connection Directory. On Android it's at the bottom of the BBS list, and its BBSes appear when you search. DialComm downloads the newest list from telnetbbsguide.com by itself each month and keeps a copy for offline use; the list is credited to The BBS Corner / The Telnet BBS Guide wherever it's shown.

## Windows 1.7.5 – November 3, 2026

**Changed**
- **Always opens on Home.** DialComm now starts on the ribbon's Home tab every time, where Rapid Connect and the Directory are, instead of the tab you used last.

## Windows 1.7.4 / Android 1.9.1 – November 3, 2026

**New**
- **Featured BBSes.** Jungle BBS (bbs.junglebbs.com), Jungle STS (junglebbs.com) and Land of the Lost (landofthelost.ca, port 2300) are now at the top of the Connection Directory and Rapid Connect, on Windows and Android. New installs start with them, and existing directories get them added once. Ones you already had keep their call history and logon details.

## Windows 1.7.3 – November 2, 2026

**New**
- **Clearer ribbon.** Each group of buttons is now its own panel with a label strip underneath, every button is a visible tile, and the tab you're on is marked in orange, so the options are easy to tell apart at a glance.

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
