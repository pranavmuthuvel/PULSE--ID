# 🚨 PULSE ID — AI Emergency Medical Identity System
### Team: Stellar Minds | HF-26-087

---

## 🚀 Quick Setup (15 minutes)

### Step 1 — Install Dependencies
```bash
cd pulse-id
npm install
```

### Step 2 — Add Firebase Config
Open `src/firebase.js` and replace with your Firebase config:
```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",           // From Firebase Console
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

### Step 3 — Add Claude API Key
Open `src/services/claudeService.js` and replace:
```js
const CLAUDE_API_KEY = "YOUR_CLAUDE_API_KEY"; // From console.anthropic.com
```

### Step 4 — Run Locally
```bash
npm start
```
App opens at http://localhost:3000

### Step 5 — Deploy to Firebase
```bash
npm install -g firebase-tools
firebase login
firebase init hosting   # select your project, set public dir = "build"
npm run build
firebase deploy
```
Your live URL: https://YOUR_PROJECT.web.app

---

## 🔑 Getting Your Keys

### Claude API Key
1. Go to https://console.anthropic.com
2. Sign up → API Keys → Create Key
3. Copy the key (starts with sk-ant-...)

### Firebase Setup
1. Go to https://console.firebase.google.com
2. Create project → name it "pulse-id"
3. Add Web App → copy firebaseConfig
4. Enable Authentication → Anonymous sign-in
5. Create Firestore Database → Start in test mode
6. Enable Hosting

---

## 🏗️ Project Structure
```
pulse-id/
├── src/
│   ├── App.js              # Main app + routing
│   ├── App.css             # Full design system
│   ├── i18n.js             # Tamil, Hindi, Bengali, English translations
│   ├── firebase.js         # Firebase config (ADD YOUR KEYS HERE)
│   ├── components/
│   │   ├── LandingPage.js  # Home screen
│   │   ├── ProfileBuilder.js # Patient profile + voice input
│   │   ├── MyQR.js         # QR code display
│   │   ├── EmergencyScan.js # Doctor emergency view + AI summary
│   │   ├── DrugCheck.js    # Drug interaction detector
│   │   └── LanguageSelector.js # Language switcher
│   └── services/
│       ├── claudeService.js  # Claude AI integration (ADD API KEY HERE)
│       └── firebaseService.js # Firestore CRUD
├── public/
│   └── index.html
├── package.json
└── firebase.json
```

---

## ✨ Features
- 🔍 **QR Emergency Identity** — Scan patient QR for instant medical summary
- 🤖 **AI Emergency Summary** — Claude AI generates prioritized clinical brief
- 💊 **Drug Interaction Detection** — AI flags dangerous drug combinations
- 🌐 **Multilingual** — Tamil, Hindi, Bengali, English
- 🎤 **Voice Input** — Speak to fill profile or check drugs
- 🔒 **Two-tier Security** — Emergency view (public) + Full records (OTP)
- 🏥 **Hospital Routing** — AI recommends nearest equipped hospital

---

## 🎤 Demo Flow for Judges
1. Open app → Create a patient profile (use voice in Tamil)
2. Show the generated QR code
3. Scan QR (or open in another tab with ?scan=ID)
4. Watch AI generate emergency summary
5. Switch language to Tamil → Show same summary in Tamil
6. Go to Drug Check → Type "Ibuprofen" → Show interaction warning
7. Show OTP protection for full records

---

Built with ❤️ by Stellar Minds for HackForge '26
