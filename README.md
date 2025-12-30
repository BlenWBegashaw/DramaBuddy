# DramaBuddy

[![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)
[![TMDb](https://img.shields.io/badge/TMDb-01d277?style=for-the-badge&logo=the-movie-database&logoColor=white)](https://www.themoviedb.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge&logo=opensource)](https://opensource.org/licenses/MIT)

**Drama Buddy** is a feature-rich Flutter application built for Korean drama fans. It combines a personal watch-list manager with a discovery engine powered by the TMDb API and a curated TikTok social feed.

---

## 📖 Table of Contents
- [Features](#-features)
- [Demo](#-demo)
- [Tech Stack](#-tech-stack)
- [App Architecture](#-app-architecture)
- [Installation](#-installation)
- [Project Structure](#-project-structure)
- [Future Roadmap](#-future-roadmap)
- [Acknowledgments](#-acknowledgments)
- [License](#-license)

---

## Demo

| Login Page | Home Page | MyDramas Page | Search Screen |
| :---: | :---: | :---: | :---: |
| <img src="assets/9.png" width="200" /> | <img src="assets/2.png" width="200" /> | <img src="assets/6.png" width="200" /> | <img src="assets/5.png" width="200" /> |

| TikTok Feed | Profile Page | KDrama Details Page | Wrapped Screen |
| :---: | :---: | :---: | :---: |
| <img src="assets/12.png" width="200" /> | <img src="assets/8.png" width="200" /> | <img src="assets/10.png" width="200" /> <br> <img src="assets/11.png" width="200" /> | <img src="assets/13.png" width="200" /> |

---

## ✨ Features

### 📺 Drama Tracking & Management
* **Status Organization:** Categorize shows into *Watching*, *Completed*, or *Planned*.
* **Episode Tracking:** Keep a precise log of which episode you are on.
* **Ratings & Reviews:** Save personal thoughts and star ratings locally.
* **Smart Sorting:** Organize your list by Title, Release Year, Rating, or Date Added.

### 📊 Monthly Wrapped (Demo)
* Visual summary of your drama consumption for the month.
* Shows total dramas completed, highest-rated picks, and most-watched genres.

### 📱 TikTok K-Drama Feed
* **Dynamic Discovery:** Scroll through trending clips via popular hashtags.
* **Customization:** Add your own hashtags and favorite them for quick access.
* **Seamless Viewing:** Watch clips via in-app WebView or jump directly to the TikTok app.

---

## 🚀 Tech Stack

* **Framework:** [Flutter](https://flutter.dev/)
* **Language:** [Dart](https://dart.dev/)
* **Database/Storage:** SharedPreferences (Local)
* **External APIs:** TMDb (The Movie Database)
* **Plugins:** 
  * `webview_flutter` for TikTok content.
  * `url_launcher` for external links.
  * `http` for API requests.

---

## 🏗️ App Architecture

DramaBuddy follows a **modular, layered architecture** to keep UI, business logic, and data handling cleanly separated.  

### 1️⃣ Layers

1. **Presentation Layer (UI / Screens / Widgets)**
   - Screens: Dashboard, MyDramas, Search, TikTok Feed, Profile, KDrama Details, Wrapped Screen.
   - Widgets: Reusable UI components like cards, lists, buttons, and tabs.
   - Responsibility: Handles displaying data and user interactions.

2. **Business Logic Layer (Controllers / State Management)**
   - Uses **StatefulWidgets** and **TabControllers** for dynamic content.
   - Sorting, filtering, and local caching logic are handled here.

3. **Data Layer (Models & Services)**
   - Models: Represent KDrama objects, user reviews, and watch status.
   - Services: Handle API requests to **TMDb**.
   - Local Storage:  stores favorites, watchlists, and settings.
   - Offline Data: singleton simulates persistent local database.

### 2️⃣ Data Flow

```
User Interaction
      │
      ▼
Presentation Layer (Screens/Widgets)
      │
      ▼
Business Logic Layer (State, Controllers)
      │
      ▼
Data Layer
   ├─ Local Storage (SharedPreferences)
   └─ Remote API 
      │
      ▼
Response / Data Updates
      │
      ▼
Business Logic Layer updates state
      │
      ▼
Presentation Layer reflects changes
```

### 3️⃣ Key Components

- Dashboard Screen: Tab-based overview of Watching, Completed, and Planned dramas.
- KDrama Detail Screen: Detailed info, ratings, and review UI.
- TikTok Feed (Demo): Scrollable trending KDrama clips (WebView demo only in public version).
- Search Screen: Add or search hashtags for TikTok feed.
- Monthly Wrapped: Visual summary dashboard (offline demo data).

### 4️⃣ Notes

- **Private Repo Version:** Full TMDb API and TikTok feed logic.  
- **Public Portfolio Version:** Only UI demos, screenshots, and architecture explanation. Sensitive code and API keys are hidden.

---



## 📁 Project Structure

```text
lib/
├── models/       # Data models (KDrama, Review, etc.)
├── data/         # Singleton logic and local data handlers
├── services/     #  API calls and network logic
├── screens/      # Flutter pages (Dashboard, Feed, Details)
├── widgets/      # Shared/Reusable UI components
└── theme/        # Style definitions (Colors, Fonts)
```


---

## 🌟 Acknowledgments

- Korean Drama Fans & Creators
- The Flutter Community

---

## 📝 License

© 2025 Blen Begashaw
All rights reserved. 

This repository is provided for portfolio purposes only. 
Reuse, redistribution, or commercial use is prohibited without permission.
