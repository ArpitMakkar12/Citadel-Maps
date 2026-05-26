<div align="center">
  <h1 align="center">📍 Citadel Maps</h1>
  <p align="center">
    An intelligent, safety-aware navigation tool designed to enhance urban safety, especially for women.
    <br />
    <a href="#about-the-project"><strong>Explore the features »</strong></a>
    <br />
    <br />
    <a href="https://arpitmakkar12.github.io/City-Sakhi-AI/">View Demo</a>
    ·
    <a href="https://youtu.be/zZGkUzhAMv0">Watch the Video</a>
    ·
    <a href="https://github.com/ArpitMakkar12/City-Sakhi-AI/issues">Report Bug</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#key-features">Key Features</a></li>
    <li><a href="#built-with">Built With</a></li>
    <li><a href="#getting-started">Getting Started</a></li>
    <li><a href="#configuration">Configuration</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

---

## About The Project

Navigating urban environments can be challenging, with safety being a primary concern for many, especially women. SafeRoute AI is a web-based mapping application designed to address this challenge. Instead of just finding the fastest route, it calculates the **safest** route by analyzing crowdsourced data on potential risks like poorly lit areas, harassment incidents, or overly crowded places.

This project leverages the power of the Google Maps Platform and Firebase to provide a real-time, data-driven, and intuitive user experience.

---
<a href="https://arpitmakkar12.github.io/City-Sakhi-AI/">View Demo</a>

## Key Features

* **🗺️ Interactive Map:** A smooth, familiar interface built with the Google Maps JavaScript API.
* **🔥 Real-time Safety Data:** Displays safety reports from a live Firebase Firestore database.
* **🎨 Color-Coded Risk Visualization:** Different incident types are shown with distinct, colored "blob" markers (Red for incidents, Yellow for poor lighting, etc.).
* **💯 Advanced Safety Scoring:** A unique algorithm calculates an intuitive safety score (from 0 to 100) for potential routes.
* **🚦 Risk-Aware Routing:** Displays multiple walking alternatives color-coded by their calculated risk level:
    * **Green:** The Safest Route
    * **Yellow:** Moderate Risk
    * **Red:** High Risk
    * **Blue:** Other Low-Risk Alternatives
* **⏱️ Multi-Modal Duration Estimates:** The info panel provides travel time estimates for Car, Bike, Public Transit, and Walking for comparison.
* **🌗 Dark/Light Theme:** A sleek theme toggle allows users to switch the map's appearance for comfort in different lighting conditions.

---

## Built With

This project was built using a range of modern web technologies and platforms.

* **Frontend:**
    * HTML5
    * CSS3
    * JavaScript (ES6+)
* **Styling:**
    * [Tailwind CSS](https://tailwindcss.com/)
* **APIs & Platforms:**
    * [Google Maps Platform](https://maps.google.com/) (Maps JavaScript API, Directions API, Places API)
    * [Google Firebase](https://firebase.google.com/) (Firestore Database)

---

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

* A modern web browser (e.g., Google Chrome, Firefox).
* A code editor (e.g., [Visual Studio Code](https://code.visualstudio.com/)).
* [Git](https://git-scm.com/downloads) installed on your machine.

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git)
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd YOUR_REPOSITORY
    ```
3.  **Follow the configuration steps below.**

---

## Configuration

This project requires API keys from Google Maps and Firebase to function. To keep these keys secure, you must create a `config.js` file that is **not** checked into version control.

1.  **Get your API Keys:**
    * Create a project on [Google Cloud Console](https://console.cloud.google.com/) and enable the **Maps JavaScript API**, **Directions API**, and **Places API**. Generate an API Key.
    * Create a project on [Firebase](https://console.firebase.google.com/), create a web app, and get your Firebase configuration object.
    * Set up a **Firestore Database** in your Firebase project.

2.  **Create `config.js` file:**
    In the root of your project folder, create a new file named `config.js` and add the following content, pasting your keys where indicated:

    ```javascript
    // config.js

    const GOOGLE_MAPS_API_KEY = "PASTE_YOUR_GOOGLE_MAPS_API_KEY_HERE";

    const firebaseConfig = {
      apiKey: "PASTE_YOUR_FIREBASE_API_KEY_HERE",
      authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
      projectId: "YOUR_PROJECT_ID",
      storageBucket: "YOUR_PROJECT_ID.appspot.com",
      messagingSenderId: "YOUR_SENDER_ID",
      appId: "YOUR_APP_ID"
    };
    ```

3.  **Create `.gitignore` file:**
    To prevent your secret keys from being uploaded to GitHub, create a file named `.gitignore` in the root of your project and add the following line to it:

    ```
    config.js
    ```

4.  **Update `index.html`:**
    Make sure your `index.html` file correctly loads `config.js` and uses the variables. (The final version of the code in our discussion does this).

---

## Usage

1.  Open the `index.html` file in your browser (preferably using a local server extension like VS Code's "Live Server").
2.  The map will load, showing safety data in your area.
3.  Use the input fields to enter a starting point and a destination.
4.  Click "Find Safest Route."
5.  The map will display alternative walking routes, color-coded by safety.
6.  The info panel will show the score of the safest route and the estimated duration for different travel modes.
7.  Use the sun/moon icon in the top-right to toggle between light and dark themes.

---

## Acknowledgments

This project was developed by a dedicated team of students.

* **Harshita Jain** - [GitHub Profile](https://github.com/harshita25221)
* **Millee Mittal** - [GitHub Profile](https://github.com/Millee-24)
* **Ashima** - [GitHub Profile](https://github.com/AshimaGosain)
* **Arpit Makkar** - [GitHub Profile](https://github.com/ArpitMakkar12)

*(Note: Please replace the placeholder GitHub profile links with the correct ones.)*
