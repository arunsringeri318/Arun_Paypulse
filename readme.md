# 💳 Paypulse v10.01 | Instant UPI Payment QR POS Terminal

![Version](https://img.shields.io/badge/Version-v10.01-indigo?style=for-the-badge)
![PWA Ready](https://img.shields.io/badge/PWA-Installable-emerald?style=for-the-badge)
![Firebase RTDB](https://img.shields.io/badge/Cloud_Sync-Firebase_RTDB-amber?style=for-the-badge)
![Single File Architecture](https://img.shields.io/badge/Architecture-Single_File_HTML5-blue?style=for-the-badge)

**Paypulse** is a modern, fast, and responsive Progressive Web App (PWA) Point-of-Sale (POS) terminal designed for merchants, retail counters, and businesses to generate instant UPI payment QR codes, track daily revenue, manage multiple payee UPI accounts, and synchronize data seamlessly across devices in real time.

---

## ✨ Key Features

### ⚡ Instant UPI QR Generation & Sharing
- **Dynamic QR Code Engine**: Generates high-contrast, scannable UPI payment QR codes (`upi://pay?...`) compatible with Google Pay, PhonePe, Paytm, BHIM, CRED, and all banking UPI apps.
- **Branded Payment Receipt Cards**: Exports high-resolution PNG payment cards (`720×1040`) complete with merchant details, payable amount, exact date/time stamp, and embedded QR code.
- **1-Tap Sharing & Printing**: Share payment cards directly via the Web Share API, launch direct WhatsApp chats with the payee, copy raw UPI intent links, download PNG receipts, or print directly from the terminal.

### 🧮 Dual Terminal Input Modes
- **Quick Entry Mode**: Tactile POS numpad with Indian Rupee (`en-IN`) comma formatting and 1-tap preset increment buttons (`+₹10`, `+₹50`, `+₹100`, `+₹500`, `+₹1k`).
- **Calculator Mode**: Built-in arithmetic expression evaluator (`+`, `-`, `×`, `÷`, parentheses) allowing merchants to total multiple items directly before generating the QR code.
- **Audio Feedback**: Subtle Web Audio API synthesizer click/beep feedback (toggleable from the system menu).

### 🏦 Multi-Payee Account Manager
- **No Accidental Selection**: Starts clean with no payee pre-selected until explicitly chosen.
- **Instant Search & Filtering**: Filter accounts in real time by payee business name or UPI handle.
- **Custom Reordering**: Rearrange payee priority order (`Move Up` / `Move Down`) directly from each card's 3-dot action menu.
- **Bulk Operations & Backups**:
  - Add single or bulk payees via comma-separated lines (`UPI_ID, Business Name, Phone`).
  - Import and export payee lists in `.json` or `.csv` formats.

### 📊 Live Earnings Analytics & Transaction Logs
- **Live Today's Earnings Banner**: Real-time calculation of total generated collections for the current day.
- **Filtered Payee Earnings Card**: Automatically appears when filtering logs by a specific UPI ID, displaying total revenue and transaction count for that account.
- **Compact Payee Breakdown Modal**: Click the filtered earnings card to inspect itemized timestamps and amounts, edit recorded amounts, delete entries, or share a formatted text summary report.
- **Advanced Filtering & CSV Export**: Filter logs by **All Time**, **Today**, **This Week**, or a custom **From Date → To Date** range, and export records to `.csv`.
- **1-Click Transaction Reuse**: Reuse any historical log entry to automatically select the payee, populate the exact amount, and scroll back to the terminal.

### ☁️ Real-Time Cloud Sync (Firebase Realtime Database)
- **Multi-Device Synchronization**: Automatically syncs payee lists, account ordering, transaction logs, and active theme preferences across devices.
- **Hybrid SDK + REST Failover**: Uses the Firebase JS SDK when hosted in authenticated environments and seamlessly switches to direct HTTPS REST polling when deployed statically on GitHub Pages.
- **Live Header Status Indicator**: Real-time connection badge (`Syncing` / `Synced ✓`) and manual `Sync Now` trigger inside the Cloud Backup modal.

### 🎨 5 Executive Color Themes
Switch instantly from the header palette menu:
1. 🛡️ **Platinum Executive** *(Default)* — Clean light slate with vibrant indigo header & colorful avatar badges.
2. 💎 **Royal Sapphire** — Deep midnight dark mode with glowing indigo accents.
3. 👑 **Imperial Gold** — Obsidian dark UI with warm amber and gold highlights.
4. 💚 **Regal Emerald** — Deep jade green executive theme.
5. 🍷 **Crown Burgundy** — Rich velvet wine dark theme.

---

## 🚀 Deployment & Hosting

Paypulse is engineered as a **zero-build, single-file web application (`index.html`)**. No Node.js, bundlers, or build steps are required.

### Option 1: GitHub Pages (Recommended)
1. Fork or upload `index.html` to a GitHub repository.
2. Navigate to **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**, choose `main` (or `master`) and `/ (root)`, then click **Save**.
4. Your live POS terminal will be accessible via HTTPS, enabling full PWA installation and automatic cloud sync.

### Option 2: Local HTTP Server
Because modern browsers enforce CORS restrictions on ES module scripts (`<script type="module">`) over the `file://` protocol, serve the folder over HTTP for local testing:

```bash
# Using Python 3
python -m http.server 8080

# Or using Node.js serve
npx serve .
```
Then open `http://localhost:8080` in your browser.

---

## 📱 Installing as a Progressive Web App (PWA)

Paypulse dynamically generates an inline Web App Manifest and registers a Service Worker when served over HTTPS:
- **Android (Chrome / Edge / Samsung Internet)**: Tap the **⋮** menu → **Add to Home Screen** or **Install App**.
- **iOS (Safari)**: Tap the **Share** icon (`⎋`) → **Add to Home Screen**.
- **Desktop (Chrome / Edge)**: Click the **Install** icon on the right side of the browser address bar.

---

## 🛠️ Tech Stack

- **Core**: HTML5, Vanilla ES6+ JavaScript (Modules)
- **Styling**: Tailwind CSS (via CDN) + CSS Custom Properties for dynamic multi-theme switching
- **Typography**: Inter & JetBrains Mono (Google Fonts)
- **QR Generation**: `QRCode.js` + HTML5 `<canvas>` API for composite receipt image rendering
- **Backend & Sync**: Firebase Realtime Database (`https://paypulse-a855a-default-rtdb.firebaseio.com`)

---

## 👨‍💻 Author & Credits

- **Developed By**: ARUN KUMAR SC, for **Arun Traders**
- **Contact**: `8105104599`
- **Release**: `Paypulse v10.01` (`Build 2026.09.26-v10.01`)

---

## 📄 License

All Rights Reserved © 2026 **Arun Traders**. Unauthorized commercial redistribution is prohibited.