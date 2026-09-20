# YUITV

<img width="1527" height="967" alt="image" src="https://github.com/user-attachments/assets/fb0f8258-857f-4a50-ad6b-ad5c79d2795a" />


# 📺 YUITV

> **Your world. Your television.**

YUITV is a modern IPTV / OTT platform built with **Flutter**, **Java 21**, and **Javalin 7**.

The project is designed to provide a clean, fast, and modern experience for watching live TV channels, movies, series, sports, and nature content from a single platform.

---

## ✨ Features

* 📺 Live TV channels
* 🇦🇿 Azerbaijani channels
* 🇷🇺 Russian channels
* 🎬 Movies
* 📺 TV series
* ⚽ Sports
* 🌿 Nature content
* 🔎 Content search
* ❤️ Favorites
* 👤 User profiles
* 📅 EPG / TV Guide
* ▶️ Live video playback
* 🌙 Modern dark UI
* 📱 Mobile support
* 📺 TV / Android TV support
* 🔐 User authentication
* ⚡ Fast backend API
* 🔄 M3U / M3U8 synchronization

---

## 🖥️ Tech Stack

### Frontend

* **Flutter**
* **Dart**
* Material Design
* Responsive UI
* TV / D-pad friendly interface

### Backend

* **Java 21**
* **Javalin 7**
* REST API
* WebSocket support

### Database

* **PostgreSQL**

### Cache & Sessions

* **Redis**

### Streaming

* **M3U**
* **M3U8**
* **HLS**
* **DASH**

---

## 🏗️ Architecture

```text
┌─────────────────────────────────────────────┐
│                  YUITV                      │
└─────────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────┐
│                 Flutter                     │
│                                             │
│  Home │ Channels │ Movies │ Series │ Sport │
│                                             │
└─────────────────────┬───────────────────────┘
                      │
                  REST / WS
                      │
                      ▼
┌─────────────────────────────────────────────┐
│              Javalin 7                     │
│               Java 21                      │
│                                             │
│ Auth │ API │ EPG │ Catalog │ Favorites     │
│                                             │
└──────────────┬──────────────┬───────────────┘
               │              │
               ▼              ▼
        ┌─────────────┐  ┌─────────────┐
        │ PostgreSQL  │  │    Redis    │
        └─────────────┘  └─────────────┘
               │
               ▼
        ┌─────────────────┐
        │ M3U / M3U8 /    │
        │ HLS / DASH      │
        └─────────────────┘
```

---

## 📱 Application Sections

```text
YUITV
│
├── 🏠 Home
│
├── 🇦🇿 AZ Channels
│
├── 🇷🇺 RU Channels
│
├── 🎬 Movies
│
├── 📺 Series
│
├── ⚽ Sports
│
├── 🌿 Nature
│
├── ❤️ Favorites
│
├── 📅 EPG
│
└── 👤 Profile
```

---

## 🎨 UI

YUITV uses a modern dark interface designed for both touch devices and large-screen environments.

The interface focuses on:

* Large content cards
* Clear navigation
* Fast access to live channels
* Dark theme
* Minimal visual noise
* TV remote / D-pad navigation
* Responsive layouts

---

## 🔌 API

The backend is built around a REST API.

Example endpoints:

```http
GET /api/categories

GET /api/channels

GET /api/channels/{id}

GET /api/movies

GET /api/series

GET /api/sports

GET /api/nature

GET /api/epg

GET /api/favorites

POST /api/auth/login

POST /api/auth/register
```

---

## 📡 Content Model

A channel or stream can be represented by data similar to:

```json
{
  "id": 1,
  "title": "AzTV",
  "type": "LIVE",
  "language": "AZ",
  "category": "TV",
  "logo": "https://example.com/logo.png",
  "stream_url": "https://example.com/stream.m3u8",
  "is_live": true
}
```

The `language` field allows YUITV to support additional languages in the future.

For example:

```text
AZ
RU
EN
TR
```

---

## 📂 Project Structure

```text
yuitv/
│
├── frontend/
│   └── flutter/
│       ├── lib/
│       │   ├── core/
│       │   ├── features/
│       │   │   ├── home/
│       │   │   ├── channels/
│       │   │   ├── movies/
│       │   │   ├── series/
│       │   │   ├── sports/
│       │   │   ├── nature/
│       │   │   ├── player/
│       │   │   ├── favorites/
│       │   │   └── profile/
│       │   │
│       │   ├── widgets/
│       │   └── main.dart
│       │
│       └── pubspec.yaml
│
├── backend/
│   └── java/
│       ├── src/
│       ├── resources/
│       └── pom.xml
│
├── database/
│   └── migrations/
│
├── docker/
│
└── README.md
```

---

## 🚀 Getting Started

### Requirements

Make sure you have installed:

* Flutter SDK
* Dart SDK
* Java 21
* Maven
* PostgreSQL
* Redis

---

### Clone the repository

```bash
git clone https://github.com/your-username/yuitv.git

cd yuitv
```

---

### Run Flutter

```bash
cd frontend/flutter

flutter pub get

flutter run
```

---

### Run Backend

```bash
cd backend/java

mvn clean install

mvn exec:java
```

---

## 🧪 Development

During development, the Flutter application can run with mock content before connecting to the backend.

Example:

```text
Flutter UI
    │
    ▼
Mock Data
    │
    ▼
UI Development
```

Later:

```text
Flutter
    │
    ▼
Javalin 7 API
    │
    ├── PostgreSQL
    ├── Redis
    └── Stream Catalog
```

---

## 🔐 Security

Security is an important part of YUITV.

Planned security features include:

* Secure authentication
* Password hashing
* Token-based sessions
* Role-based access control
* API validation
* Rate limiting
* Secure configuration
* Environment-based secrets
* HTTPS in production

YUITV does not aim to bypass DRM, authentication systems, or provider access controls.

Only streams and content that the project has permission to use should be integrated.

---

## 📺 TV Support

YUITV is designed with TV platforms in mind.

The UI can be adapted for:

* Android TV
* Google TV
* Smart TV environments
* Large screens
* Remote controls
* D-pad navigation

The TV interface prioritizes:

```text
Remote
   │
   ▼
Focus
   │
   ▼
Navigation
   │
   ▼
Content
```

---


## 🌍 Future

YUITV is being designed as a scalable platform rather than a simple IPTV player.

Possible future features:

* 🌐 Multi-language interface
* 👥 Multiple profiles
* 🔔 Notifications
* 🧠 Personalized recommendations
* 📊 Watch history
* ☁️ Cloud synchronization
* 📱 Mobile applications
* 📺 TV applications
* 🖥️ Web client
* 🔑 Subscription system

---

## 🤝 Contributing

Contributions, ideas, and improvements are welcome.

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/my-feature
```

3. Commit your changes

```bash
git commit -m "Add my feature"
```

4. Push the branch

```bash
git push origin feature/my-feature
```

5. Open a Pull Request

---

## 📜 License

This project is currently under development.

License information will be added when the project reaches its first public release.

---

## 👨‍💻 Author

**Yusif Rahimov**

Building YUITV with:

```text
Flutter
+
Java 21
+
Javalin 7
+
PostgreSQL
+
Redis
```

---

# ⭐ YUITV

**Your world. Your television.**

Built with ❤️ and code.
