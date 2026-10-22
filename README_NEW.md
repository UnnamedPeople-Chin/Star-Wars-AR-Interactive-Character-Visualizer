<div align="center">

  <img src="https://raw.githubusercontent.com/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer/main/Assets/Icon/icons8-star-wars-512.png" alt="Star Wars AR Logo" width="130" style="margin-bottom: 15px;" />

  # 🌟 Star Wars AR — Interactive Character Visualizer

  **Augmented Reality brings iconic Star Wars characters to life. Point, tap, interact.**

  [![GitHub](https://img.shields.io/badge/GitHub-Repository-black?style=for-the-badge&logo=github)](https://github.com/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer)
  [![Unity](https://img.shields.io/badge/Unity-6.0.4f1-black?style=for-the-badge&logo=unity&logoColor=white)](https://unity.com)
  [![Vuforia](https://img.shields.io/badge/Vuforia-11.4.4-blue?style=for-the-badge&logo=firebase&logoColor=white)](https://developer.vuforia.com)
  [![License](https://img.shields.io/badge/License-Educational-green?style=for-the-badge)](LICENSE)
  [![Demo Video](https://img.shields.io/badge/Demo-45s_Teaser-FF6B35?style=for-the-badge&logo=youtube&logoColor=white)](STAR_WARS_AR_DEMO.mp4)

  <p align="center">
    <a href="#-demo-video"><strong>View Demo »</strong></a>
    <br />
    <br />
    <a href="#-features">Features</a> •
    <a href="#-characters--targets">Characters</a> •
    <a href="#-tech-stack">Tech Stack</a> •
    <a href="#-getting-started">Setup</a> •
    <a href="#-team">Team</a>
  </p>

</div>

---

## 📌 Overview

**Star Wars AR** is an immersive mobile AR experience that brings the galaxy to your fingertips. Scan Star Wars posters — 6 iconic characters spawn in 3D with interactive animations, real-time audio, and character info panels. Built with **Unity 6 + Vuforia**, deployed for **Android with ARCore**.

**Status:** ✅ Production Ready | **Targets:** 6 Characters | **Platforms:** Android 9.0+ (API 29+) | **Demo:** 45sec @ 1920×1080 24fps

---

## 🎬 Demo Video

<p align="center">
  <a href="https://media.githubusercontent.com/media/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer/main/STAR_WARS_AR_DEMO.mp4">
    <img src="https://raw.githubusercontent.com/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer/main/readme-assets/frame-12.jpg" alt="Star Wars AR Demo" style="border-radius: 8px; box-shadow: 0 4px 14px rgba(0,0,0,0.2);" width="100%" />
  </a>
</p>

<p align="center"><em>45-second teaser: hero title → character cards → tap interaction → montage → CTA. <a href="https://media.githubusercontent.com/media/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer/main/STAR_WARS_AR_DEMO.mp4">Watch now</a>.</em></p>

---

## ✨ Features

| Feature | Details |
|---------|---------|
| 🎯 **AR Image Tracking** | Detect 6 Star Wars character posters; instant 3D spawn (<2s) |
| 👆 **Tap to Animate** | Trigger character attack animations + voice lines on tap |
| 📋 **Info Panel** | Access character stats (name, affiliation, weapon, quote) |
| 🔊 **Sonic Branding** | Auto-play character audio on spawn; iconic VO on interaction |
| 🖱️ **Multi-Touch** | 1-finger rotate + 2-finger zoom; smooth controls on mobile |
| ☁️ **Vuforia Powered** | Robust image tracking across lighting conditions |

---

## 🎯 Characters & Targets

| Character | Affiliation | Weapon | Status |
|-----------|------------|--------|--------|
| **Darth Vader** | Dark Side (Sith) | Lightsaber Red | ✅ Rigged + Animated |
| **AT-AT** | Galactic Empire | Blaster Cannon | ✅ Full 3D Model |
| **Luke Skywalker** | Jedi / Rebellion | Lightsaber Blue | ✅ Rigged + Animated |
| **Yoda** | Jedi Council | Lightsaber Green | ✅ Rigged + Animated |
| **R2-D2** | Rebellion | Utilities | ✅ Full 3D Model |
| **X-Wing** | Rebellion | Laser Cannons | ✅ Full 3D Model |

**Scan these posters** (`Assets/Image Target/*.jpg`) to spawn characters. Print or display on-screen.

---

## 🛠️ Tech Stack

| Layer | Tech |
|-------|------|
| **Engine** | Unity 6.0.4f1 |
| **AR SDK** | Vuforia 11.4.4 (image tracking) |
| **Input** | Unity InputSystem (multi-touch) |
| **UI** | TextMesh Pro, Figma Bridge |
| **Audio** | Unity AudioSource + WAV/MP3 |
| **3D Content** | Blender, Mixamo, ActorCore (modeling/rigging/animation) |
| **Target Platform** | Android 12+ with ARCore |

---

## 📂 Project Structure

```
Assets/
├── AR StarWars.unity              # Main scene (6 characters + UI)
├── Image Target/                  # 6 character poster JPGs
├── Audio/                         # Music, SFX, voice lines
├── [Darth Vader, AT-AT, Luke...]  # Per-character folders (3D + animations)
├── Prefabs/                       # Canvas, UI panels, Quit button
├── Sprites/                       # Menu icons, UI graphics
├── CharacterInteraction.cs        # Tap handler + animation trigger
├── TapCharacter.cs                # Audio playback on tap
├── UIManager.cs                   # Menu & panel control
├── ObjectTransform.cs             # Rotation + zoom logic
└── QuitAplikasi.cs                # Exit handler

ProjectSettings/
├── ProjectVersion.txt
└── XRSettings.asset               # Vuforia config

Packages/
└── manifest.json                  # Dependencies (Vuforia, InputSystem, etc.)
```

---

## 💻 Getting Started

### 1. Prerequisites
- **Unity 6.0.4f1** (download from [unity.com](https://unity.com))
- **Vuforia Engine 11.4.4** (included via Packages/manifest.json)
- **Android phone** with ARCore support (API 29+)

### 2. Open in Unity
```bash
git clone https://github.com/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer.git
cd Star-Wars-AR-Interactive-Character-Visualizer
```

Open folder in Unity Hub → wait 2–5 minutes for import.

### 3. Vuforia License Setup (One-time)
1. Create free account at [developer.vuforia.com](https://developer.vuforia.com)
2. Generate **License Key** in dashboard
3. In Unity: `Vuforia Engine` → `License Manager` → paste key

### 4. Build for Android
```
File → Build Settings
├─ Switch Platform → Android
├─ Player Settings: Min API 30+, enable ARCore
└─ Build & Run
```

### 5. Use the App
- Print or display on-screen: `Assets/Image Target/` (6 JPGs: Vader, Luke, Yoda, R2-D2, X-Wing, AT-AT)
- Run app on smartphone
- Point camera at poster → character spawns in <2 seconds
- **1-finger tap:** trigger attack animation + play voice line
- **1-finger drag:** rotate character
- **2-finger pinch:** zoom in/out
- **UI buttons:** How To Play, Back, Quit

---

## 👥 Team

Developed by **Kelompok 5** for the AR Project:

- **Kafka Nafisa** — Project Manager
- **Anisa Aulia** — UI/UX Designer
- **Jizdan Yuflikh R** — 3D Artist, Animator, QA
- **Nazriel Farras Khairiya Putra Sisworo** — Developer, Sound Designer

---

## 📝 License & Disclaimer

**Star Wars** © Lucasfilm Ltd./Disney. This is an **educational, non-commercial** project for academic portfolio purposes only.

**Code: MIT License** | Art & Audio: **Educational Use** | Vuforia: [EULA](https://developer.vuforia.com/terms)

---

<div align="center">
  <sub>© 2026 Star Wars AR. May the Force be with you. 🚀</sub>
</div>
