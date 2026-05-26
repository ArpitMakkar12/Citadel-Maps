<div align="center">

<img src="https://img.shields.io/badge/status-live-00ffaa?style=for-the-badge&labelColor=0a0f1e" alt="Status">
<img src="https://img.shields.io/badge/license-MIT-00d4ff?style=for-the-badge&labelColor=0a0f1e" alt="License">
<img src="https://img.shields.io/badge/built%20with-leaflet%20%2B%20firebase-ff3c3c?style=for-the-badge&labelColor=0a0f1e" alt="Stack">
<img src="https://img.shields.io/badge/api%20keys-zero%20required-00ffaa?style=for-the-badge&labelColor=0a0f1e" alt="No API Keys">

<br /><br />

```
  ██████╗██╗████████╗ █████╗ ██████╗ ███████╗██╗
 ██╔════╝██║╚══██╔══╝██╔══██╗██╔══██╗██╔════╝██║
 ██║     ██║   ██║   ███████║██║  ██║█████╗  ██║
 ██║     ██║   ██║   ██╔══██║██║  ██║██╔══╝  ██║
 ╚██████╗██║   ██║   ██║  ██║██████╔╝███████╗███████╗
  ╚═════╝╚═╝   ╚═╝   ╚═╝  ╚═╝╚═════╝ ╚══════╝╚══════╝
███╗   ███╗ █████╗ ██████╗ ███████╗
████╗ ████║██╔══██╗██╔══██╗██╔════╝
██╔████╔██║███████║██████╔╝███████╗
██║╚██╔╝██║██╔══██║██╔═══╝ ╚════██║
██║ ╚═╝ ██║██║  ██║██║     ███████║
╚═╝     ╚═╝╚═╝  ╚═╝╚═╝     ╚══════╝
```

### **Navigate smarter. Stay safer.**
*A real-time, crowdsourced safety navigation tool built for urban environments — especially for women.*

<br />

[![View Demo](https://img.shields.io/badge/🌐_View_Live_Demo-0a0f1e?style=for-the-badge&logo=googlechrome&logoColor=00d4ff)](https://arpitmakkar12.github.io/Citadel-Maps/)
[![Watch Video](https://img.shields.io/badge/▶_Watch_Demo_Video-0a0f1e?style=for-the-badge&logo=youtube&logoColor=ff3c3c)](https://youtu.be/zZGkUzhAMv0)
[![Report Bug](https://img.shields.io/badge/🐛_Report_a_Bug-0a0f1e?style=for-the-badge&logo=github&logoColor=ffffff)](https://github.com/ArpitMakkar12/Citadel-Maps/issues)

</div>

---

## 📖 Table of Contents

- [The Problem We Solved](#-the-problem-we-solved)
- [How It Works](#-how-it-works)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Firebase Setup](#-firebase-setup)
- [Project Structure](#-project-structure)
- [Safety Algorithm](#-safety-algorithm)
- [The Team](#-the-team)

---

## 🎯 The Problem We Solved

> *"In India, a woman is assaulted every 16 minutes. Most navigation apps route you fast — not safe."*

Standard GPS apps optimize for **speed**. Citadel Maps optimizes for **safety**. Using real, crowdsourced incident data, it scores every possible route and highlights the one least likely to put you at risk — whether it's a poorly lit alley, a harassment hotspot, or an overcrowded area at night.

This isn't just a maps app. It's a **community safety layer** on top of the city you already navigate.

---

## ⚙️ How It Works

```
  User enters     →    Nominatim    →    OSRM fetches     →   Safety algorithm
  destination          geocodes          3 walking routes      scores each route
                       the address       (with alternatives)   against Firestore data

       ↓
  Routes displayed    ←    Color-coded    ←    Safest route
  on Leaflet map           by risk level        highlighted green
```

1. **Community reports** are stored in Firebase Firestore (`checkins` collection) with a location, type, and timestamp.
2. When you request a route, the app fetches all walking alternatives from **OSRM** (OpenStreetMap Routing Machine).
3. Each route is **scored 0–100** by checking how many danger points fall within 250m of the path, weighted by severity and normalized by route length.
4. All routes are drawn on the map — color-coded by risk. The safest one is highlighted in **green** and snapped to the top.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🗺️ **Interactive Map** | Powered by Leaflet.js + CartoDB tiles. Smooth, responsive, mobile-friendly. |
| 🔴 **Live Safety Overlay** | Real-time danger markers streamed from Firebase Firestore. |
| 🧮 **Safety Score (0–100)** | Custom algorithm weighs incident density vs. route length for an honest score. |
| 🚦 **Color-Coded Routes** | Green = safest, Yellow = moderate, Red = high risk. Multiple alternatives shown at once. |
| 🔍 **Smart Place Search** | Nominatim-powered autocomplete — searches the entire world, completely free. |
| ⏱️ **Multi-Modal ETAs** | Estimated travel time for walking, driving, and cycling shown together. |
| 🛡️ **Safe Zone Alerts** | Notifies you when you're within 250m of a police station or verified safe zone. |
| 🆘 **SOS Button** | One tap fires a `mailto:` with your GPS coordinates to an emergency contact. |
| 🌙 **Dark / Light Theme** | Toggle between tactical dark mode and a clean light map. |
| ⚡ **Zero API Keys** | Map, routing, and geocoding are entirely free with no billing setup required. |

### Risk Indicator Legend

| Marker | Type | Route Weight |
|---|---|---|
| 🔴 Red glow | Harassment / Incident | 5 (highest) |
| 🟡 Yellow glow | Poorly Lit Area | 3 |
| 🔵 Blue glow | Too Crowded | 1 |
| 🟢 Green glow | All Safe (community verified) | 0 |
| 🔷 Blue P | Police Station / Safe Zone | — |

---

## 🛠️ Tech Stack

**Zero paid APIs. Zero lock-in. 100% open-source mapping stack.**

| Layer | Technology | Why |
|---|---|---|
| **Maps** | [Leaflet.js](https://leafletjs.com/) v1.9.4 | Lightweight, open-source, battle-tested |
| **Map Tiles** | [CartoDB](https://carto.com/basemaps/) via OpenStreetMap | Beautiful dark/light tiles, free forever |
| **Routing** | [OSRM](https://project-osrm.org/) | Open-source router, supports walking/driving/cycling, returns route alternatives |
| **Geocoding** | [Nominatim](https://nominatim.org/) | OpenStreetMap's search engine, no key needed |
| **Database** | [Firebase Firestore](https://firebase.google.com/) | Real-time listener for live safety data |
| **Styling** | [Tailwind CSS](https://tailwindcss.com/) + custom CSS | Utility-first with a custom dark theme |
| **Fonts** | [Google Fonts](https://fonts.google.com/) — Bebas Neue, DM Sans, JetBrains Mono | Tactical, readable, distinctive |
| **Language** | Vanilla HTML5 / CSS3 / ES6+ JavaScript | No build step, no framework overhead |

---

## 🚀 Getting Started

No npm. No build tools. No API keys. Just clone and open.

### Prerequisites

- A modern browser (Chrome, Firefox, Edge)
- [Git](https://git-scm.com/) installed
- A [Firebase](https://firebase.google.com/) project with Firestore enabled *(for live safety data)*

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/ArpitMakkar12/Citadel-Maps.git
cd Citadel-Maps
```

**2. Open in your browser**
```bash
# Option A — just open the file
open index.html

# Option B — use VS Code Live Server (recommended)
# Right-click index.html → "Open with Live Server"
```

That's it. The map loads instantly. Routing and search work out of the box.

---

## 🔥 Firebase Setup

The safety data overlay requires a Firebase project. The routing and map work without it.

**1. Create a Firebase project**

Go to [console.firebase.google.com](https://console.firebase.google.com/) → New Project → Enable Firestore Database.

**2. Set Firestore rules** (allow public reads for the safety feed)

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /checkins/{doc} {
      allow read: if true;
      allow write: if request.auth != null;
    }
    match /safezones/{doc} {
      allow read: if true;
    }
  }
}
```

**3. Update the config in `index.html`**

Find this block and replace with your project's values:

```javascript
const firebaseConfig = {
    apiKey:            "YOUR_FIREBASE_API_KEY",
    authDomain:        "YOUR_PROJECT_ID.firebaseapp.com",
    projectId:         "YOUR_PROJECT_ID",
    storageBucket:     "YOUR_PROJECT_ID.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId:             "YOUR_APP_ID"
};
```

**4. Firestore data schema**

`checkins` collection — each document:
```json
{
  "type": "incident",
  "location": { "lat": 16.5062, "lng": 80.6480 },
  "timestamp": "2025-01-01T00:00:00Z"
}
```

Valid `type` values: `incident` · `unlit` · `crowded` · `safe`

`safezones` collection — each document:
```json
{
  "name": "Vijayawada Central Police Station",
  "location": { "latitude": 16.5062, "longitude": 80.6480 }
}
```

---

## 📁 Project Structure

```
Citadel-Maps/
│
├── index.html                  # The entire application (single file)
│
├── India_PublicCrime_Dataset_Final.csv   # Reference crime dataset
│
├── City Sakhi-CodeRush.pptx    # Project presentation deck
│
└── README.md                   # You are here
```

The entire app lives in a single `index.html` — no bundler, no dependencies to install, no build step.

---

## 🧮 Safety Algorithm

The scoring system is designed to be honest and length-aware so longer routes aren't unfairly penalized.

```
For each route alternative:

  1. Get all danger points within 250m of any point on the route
  2. Sum their weights:
       incident  → 5 pts
       unlit     → 3 pts
       crowded   → 1 pt
       safe      → 0 pts

  3. Normalize by route length (km):
       danger_density = total_weight / route_length_km

  4. Convert to 0–100 score:
       safety_score = max(0, 1 − danger_density / 10) × 100

  5. Route with highest score = THE SAFEST ROUTE (drawn in green)
```

**Score interpretation:**

| Score | Risk Level | Route Color |
|---|---|---|
| 80 – 100 | 🟢 Low Risk | Green |
| 50 – 79 | 🟡 Moderate Risk | Yellow |
| 0 – 49 | 🔴 High Risk | Red |

---

## 👥 The Team

Built at **CodeRush Hackathon** by a team of four students from VIT-AP University.

<table>
  <tr>
    <td align="center">
      <b>Arpit Makkar</b><br/>
      <a href="https://github.com/ArpitMakkar12">@ArpitMakkar12</a>
    </td>
    <td align="center">
      <b>Harshita Jain</b><br/>
      <a href="https://github.com/harshita25221">@harshita25221</a>
    </td>
    <td align="center">
      <b>Millee Mittal</b><br/>
      <a href="https://github.com/Millee-24">@Millee-24</a>
    </td>
    <td align="center">
      <b>Ashima Gosain</b><br/>
      <a href="https://github.com/AshimaGosain">@AshimaGosain</a>
    </td>
  </tr>
</table>

---

<div align="center">

**If this project resonates with you, leave a ⭐ — it helps others find it.**

*Built with purpose. Navigating toward safer cities.*

</div>
