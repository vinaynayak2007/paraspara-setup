# ⚠️ Install help

**Error "-0.bin is missing" / "(2)-0.bin" / "(7)-0.bin"?** Your browser renamed duplicate downloads (" (2)", " (7)"...). The setup exe looks for bins matching its own name.
- **Easiest:** download **ParasParaService-Setup-CLEAN.zip**, extract it, open the extracted folder and run the setup inside — names locked, error impossible.
- **Or:** put the 3 files in a NEW empty folder with identical base names (delete every " (n)" copy first).

**Maintainer note:** release assets come from the verified clean pipeline (exe `7d8d0f8a`, bins `80ff250d`+`5040c075`, zip `e23d3e93`). Never re-upload old builds (`edb092b3` generation = 11 AV flags).

# 🚀 Paraspara Service — Official Windows Installer

Official Windows desktop software and cloud print spooler for **Paraspara Service**.

---

## 📥 Official Downloads (v1.0.16)

### 📦 Clean ZIP Package (Recommended):
[![Download ParasParaService-Setup-CLEAN.zip](https://img.shields.io/badge/Download-ParasParaService--Setup--CLEAN.zip-00b894?style=for-the-badge&logo=zip&logoColor=white)](https://github.com/vinaynayak2007/paraspara-setup/releases/latest/download/ParasParaService-Setup-CLEAN.zip)

> **Direct Download Link:**  
> **👉 [https://github.com/vinaynayak2007/paraspara-setup/releases/latest/download/ParasParaService-Setup-CLEAN.zip](https://github.com/vinaynayak2007/paraspara-setup/releases/latest/download/ParasParaService-Setup-CLEAN.zip)**

---

### 💿 Direct Windows Setup Executable:
- **[ParasParaService-Setup.exe](https://github.com/vinaynayak2007/paraspara-setup/releases/latest/download/ParasParaService-Setup.exe)** (5.21 MB)

---

## 🆕 What's New in v1.0.16

- ✂️ **Double-copy fix** — a launched+handled print job now stops the chain immediately (no second engine ever receives the same job); kiosk twin-retry duplicates within 120 s are dropped as `Skipped-Dup`. One order = one print.
- Includes v1.0.15 duplex + parsing fixes and all earlier hardening.

> **Note:** the v1.0.16 zip extracts to a `ParasParaService-v1.0.16` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.15

- 📄 **Duplex printing** — double-sided orders print front-and-back via the print engine.
- 🔢 **Order-field parsing fix** — copies/pages/amounts parse correctly from any Firestore numeric type (string/int/double/bool); closes the data path behind the copies=61 flood.
- 🧹 **Stuck-pending cleanup** — already-done jobs are marked completed server-side immediately.
- Includes v1.0.14 Full Clean + all earlier hardening.

> **Note:** the v1.0.15 zip extracts to a `ParasParaService-v1.0.15` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.14

- 🧹 **Full Clean button** on the printer page (two-tap confirm): clears history AND purges every stuck document from all connected printer queues — clear an EPSON flood from inside the app.
- 🔤 Fixed the `??` glyphs in the history header.
- Includes v1.0.13 zero-paper-loss hardening + v1.0.12 storm defenses + v1.0.11 print engine.

> **Note:** the v1.0.14 zip extracts to a `ParasParaService-v1.0.14` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.13

- 🛡️ **Virtual-printer trap closed** — jobs can never be routed to "Microsoft Print to PDF"/XPS/Fax/OneNote (silent zero-paper loss). No physical printer = honest Failed, not a vanished job.
- 🔁 **Restart-proof flood guard** — `print_guard.dat` in ProgramData remembers processed jobs & content fingerprints across reboots; stale server backlogs cannot re-flood the printer.
- ⏱️ **Backlog pacing** — max 4 jobs per tick when a big queue arrives at once.
- Includes v1.0.12 storm defenses + v1.0.11 print engine + everything before.

> **Note:** the v1.0.13 zip extracts to a `ParasParaService-v1.0.13` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.12

- 🛑 **Reprint-storm fix** — copies hard-capped at 20, one verified print process per copy (a bogus copies=61 order can no longer spool 61 documents), printer-queue backpressure, 15 submissions/min rate limit, identical-content suppression (max 2× per 30 min, extras marked `Skipped-Dup`).
- Includes v1.0.11 bundled print engine + spooler-verified printing + everything before.

> **Note:** the v1.0.12 zip extracts to a `ParasParaService-v1.0.12` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.11

- 🖨️ **Bundled print engine** — official SumatraPDF 3.6.1 (`print_engine.exe`) installs with the app and silently prints customer PDFs/images via direct GDI. No browser needed; the Edge hand-off problem ("Done but not printed") is gone at the root.
- ✅ Every engine job is **spooler-verified**: Completed only when paper is genuinely queued; honest Failed otherwise.
- 🧠 Smart printer resolver + non-blocking queue notifications (UI stays responsive while printing).
- Includes v1.0.10 truthful verification, v1.0.9 all-format printing + multi-copy, v1.0.8 Full Scan fix, Free Trial, background PC start.

> **Note:** the v1.0.11 zip extracts to a `ParasParaService-v1.0.11` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.10

- 🔧 **"Shows Done but didn't print" bug FIXED** — the app now verifies every print through the real Windows spooler queue (`ADD_JOB` watch). A job is marked Completed only when paper is genuinely queued at the printer; failed prints now honestly report Failed (no more false "Done" for customer PDF/image uploads). Edge headless browser hand-off and silent shell-verb failures were the root cause.
- ⚡ Fails fast with a clear status when the selected printer can't be opened (wrong name / offline).
- Includes v1.0.9: all-format printing, multi-copy, security hardening; v1.0.8 Full Scan fix; Free Trial; background PC start.

> **Note:** the v1.0.10 zip extracts to a `ParasParaService-v1.0.10` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.9

- 🖨️ **Comprehensive direct printing** — PDF, JPG/JPEG/PNG/WEBP/BMP, DOC/DOCX and TXT now print correctly (Win32 spooler, full-page image spooling, Edge headless PDF, silent `/pt` via Word/WordPad/Notepad/Paint).
- 📑 **Multi-copy printing** (2, 3, …) for PDFs, photos and documents with FIFO queue order and spooler cooldown.
- 🔒 **Security hardening** — SSRF check, URL scheme validation, path-traversal guard, shell-arg sanitization, auto-cleanup of printed temp files.
- 🛡️ Print fallbacks are pure Win32 now (no powershell/system calls).
- Includes v1.0.8 Full Scan fix + Free Trial + background PC start + size/time/printer history.

> **Note:** the v1.0.9 zip extracts to a `ParasParaService-v1.0.9` folder — run the setup from inside it.

---

## 🆕 What's New in v1.0.8

- 🔧 **Full Scan fixed**: completes properly now — executable filter runs before disk stat (no more hours of wasted I/O that made it look frozen), one bad folder can't abort the scan, progress bar keeps moving, deep paths (260+ chars) no longer skipped.
- 🎁 **7-day Free Trial** for accounts without membership (persists across restarts, profile shows days left).
- 🖥️ **True background start on PC-on** — tray icon only, no window at startup.
- 📄 Print history shows document **Size** + 🕒 time + printer, persisted.
- 🛡️ All files **0/75 on VirusTotal**, Microsoft Defender undetected.

---

## ✨ Features

- **Continuous Cloud Print Spooler**: Runs a dedicated worker thread in the background on PC boot, fetching and printing incoming orders even when the software is minimized or hidden in the system tray.
- **Offline Login & Password Caching**: Secure local salt-hash credential verification allows signing in and unlocking all tools without an active internet connection.
- **Silent Windows Auto-Start**: Automatically launches on Windows startup into the system tray (`--background`) with 0% idle CPU and live status indicator.
- **Hardware MAC Binding**: Accurate single-device licensing bound directly to physical Ethernet and Wi-Fi adapter hardware.
- **Physical Thermal & Standard USB / Wi-Fi Printing**: Instant local spooling for shop counter receipts, documents, and touchless kiosk tickets.

---

## 💻 System Requirements

- **Operating System**: Windows 10 / Windows 11 (64-bit)
- **Permissions**: Standard User or Administrator
- **Architecture**: x64

---

© 2026 Paraspara Service. All Rights Reserved.
