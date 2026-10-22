# 🌟 Star Wars AR — Interactive Character Visualizer

[![Unity](https://img.shields.io/badge/Unity-6.4-black?logo=unity)](https://unity.com)
[![Vuforia](https://img.shields.io/badge/Vuforia-11.4.4-blue)](https://developer.vuforia.com)
[![License](https://img.shields.io/badge/License-Educational-green)](#lisensi)
[![Team](https://img.shields.io/badge/Kelompok-5-orange)](#tim-pengembang)

Membawa dunia Star Wars ke genggaman Anda. Aplikasi Augmented Reality ini menghadirkan karakter-karakter ikonik Star Wars dalam pengalaman interaktif real-time. Tunjukkan poster karakter ke kamera — mereka akan muncul dalam 3D, siap untuk diinteraksi.

---

## ✨ Fitur Unggulan

| Fitur | Deskripsi |
|-------|-----------|
| **AR Image Tracking** | Deteksi 6 target karakter (Darth Vader, AT-AT, Luke Skywalker, Yoda, R2-D2, X-Wing) dengan presisi tinggi |
| **Interactive Tap** | Ketuk karakter untuk memicu animasi serangan yang dinamis |
| **Info Panel** | Akses data karakter—nama, afiliasi, senjata—dengan panel UI yang responsif |
| **Sonic Branding** | Audio signature otomatis saat karakter spawn; voice lines ikonik saat diinteraksi |
| **Multi-touch Controls** | Satu jari untuk rotasi, dua jari untuk zoom; pergerakan mulus di perangkat mobile |
| **Vuforia Powered** | Engine AR stabil dengan tracking konsisten di berbagai kondisi pencahayaan |

---

## 🎯 Target Karakter & ImageTarget

| Karakter | Afiliasi | Senjata | Status |
|----------|----------|--------|--------|
| **Darth Vader** | Dark Side (Sith) | Lightsaber Merah | ✅ Implementasi Lengkap |
| **AT-AT** | Galactic Empire | Blaster Cannon | ✅ Implementasi Lengkap |
| **Luke Skywalker** | Jedi / Rebel Alliance | Lightsaber Biru | ✅ Implementasi Lengkap |
| **Yoda** | Jedi Council | Lightsaber Hijau | ✅ Implementasi Lengkap |
| **R2-D2** | Rebel Alliance | Computing/Utilities | ✅ Implementasi Lengkap |
| **X-Wing** | Rebel Alliance | Laser Cannons | ✅ Implementasi Lengkap |

**Image Target Tersedia:** Poster/gambar karakter tersimpan di `Assets/Image Target/` dengan format JPG yang dioptimalkan untuk deteksi cepat.

---

## 🏗️ Arsitektur & Alur Pengguna

### Alur Utama
```
1. Aplikasi Dibuka
   ↓
2. Main Menu Ditampilkan
   ├─ How To Play (tutorial)
   └─ Mulai Scanning
       ↓
3. Scan Mode (Kamera Aktif)
   ├─ Arahkan ke poster Star Wars
   └─ ImageTarget Terdeteksi
       ↓
4. Karakter 3D Muncul
   ├─ Audio signature diputar
   ├─ Panel informasi aktif
   └─ Siap untuk interaksi
       ↓
5. Interaksi
   ├─ Tap: Animasi serangan + Audio VO
   ├─ Geser: Rotasi karakter
   ├─ Pinch: Zoom in/out
   └─ Back: Kembali ke menu
       ↓
6. Exit / Repeat
```

### Komponen Kunci
- **CharacterInteraction.cs**: Menangani deteksi tap dan pemicu animasi
- **TapCharacter.cs**: Memutar audio signature pada karakter
- **UIManager.cs**: Kontrol alur menu dan panel informasi
- **ObjectTransform.cs**: Manajemen rotasi/zoom multi-touch
- **QuitAplikasi.cs**: Keluar aplikasi dengan aman

---

## 🛠️ Tech Stack

| Komponen | Versi | Peran |
|----------|-------|-------|
| **Engine** | Unity 6.4 | Game engine dan runtime |
| **AR SDK** | Vuforia 11.4.4 | Computer vision + image tracking |
| **Input** | Unity InputSystem 1.19.0 | Multi-touch & mouse input handling |
| **UI** | TextMesh Pro | Rendering teks dan UI HUD |
| **Audio** | Unity AudioSource | Playback musik dan VO |
| **Design Tools** | Figma Bridge 1.0.8 | Kolaborasi designer-developer |
| **3D Assets** | Blender, Mixamo, ActorCore | Modelling, rigging, animasi |

---

## 📁 Struktur Proyek

```
Star-Wars-AR-Interactive-Character-Visualizer/
├── Assets/
│   ├── AR StarWars.unity              # Scene utama (6 karakter + UI)
│   ├── Image Target/                  # 6 JPG poster karakter
│   ├── Audio/                         # Musik tema, SFX, voice lines
│   ├── [Karakter]/                    # Darth Vader, AT-AT, Luke, Yoda, R2-D2, X-Wing
│   │   ├── Models/                    # 3D mesh + rig
│   │   ├── Textures/                  # Material textures
│   │   └── Animations/                # AnimController + clips (idle, attack)
│   ├── Prefabs/                       # Canvas, Quit, UI panels
│   ├── Sprites/                       # UI icons (Main Menu, Scan, How To Play)
│   ├── Canvas.prefab & Canvas 1.prefab # UI layouts
│   ├── CharacterInteraction.cs        # Tap handler
│   ├── TapCharacter.cs                # Audio playback
│   ├── UIManager.cs                   # Menu control
│   ├── ObjectTransform.cs             # Rotation + zoom
│   ├── QuitAplikasi.cs                # Exit logic
│   └── Figma/                         # Design exports (fonts, screens)
├── ProjectSettings/
│   ├── ProjectVersion.txt             # Unity version pin
│   ├── XRSettings.asset               # Vuforia config
│   └── ...
├── Packages/
│   └── manifest.json                  # Dependencies (Vuforia 11.4.4, InputSystem, etc.)
└── README.md                          # Dokumentasi ini
```

---

## 🚀 Cara Membuka & Setup

### Prasyarat
- **Unity 6.4** (download dari [unity.com](https://unity.com))
- **Vuforia Engine 11.4.4** (sudah included di Packages/manifest.json)
- **Smartphone Android** dengan ARCore (untuk build final)

### Langkah-langkah

#### 1. Clone Repository
```bash
git clone https://github.com/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer.git
cd Star-Wars-AR-Interactive-Character-Visualizer
```

#### 2. Buka di Unity
- Launch Unity Hub → Open → pilih folder ini
- Unity akan import Assets (tunggu 2–5 menit untuk first load)

#### 3. Vuforia License Setup (One-time)
- Kunjungi [developer.vuforia.com](https://developer.vuforia.com)
- Create free Developer Account
- Generate **License Key**
- Di Unity Editor: Vuforia Engine → License Manager → paste key Anda

#### 4. Build untuk Testing
- **PC Testing**: File → Build and Run (gunakan Editor playmode atau Build UWP)
- **Android Build**:
  - File → Build Settings
  - Switch platform ke Android
  - Player settings: Target API 30+, ARCore support enabled
  - Build APK → install ke smartphone

#### 5. Gunakan Image Target
- Print atau buka gambar karakter dari `Assets/Image Target/`
- Jalankan app di smartphone
- Arahkan kamera ke poster → karakter muncul!

---

## 📊 Mekanik & Gameplay

### Deteksi & Spawn
- **Detection Distance**: ~50 cm hingga 2 meter (optimal)
- **Spawn Time**: <2 detik setelah ImageTarget terdeteksi
- **Tracking Stability**: Konsisten bahkan dengan pencahayaan rendah (Vuforia SmartTerrain)

### Tap Interaction
```csharp
OnPointerClick → Animator.SetTrigger("PlayAction") 
              → Play attack animation (0.6–1.2 detik)
              → AudioSource.Play() (VO karakter)
```

### Multi-touch Controls
- **1 Finger Drag**: Rotasi Y-axis (0.5x speed)
- **2 Finger Pinch**: Zoom in/out (0.01 scale per frame)
- **Testing di PC**: Left Mouse Drag untuk rotasi, scroll untuk zoom

### Info Panel
- **Tombol**: Aktif otomatis saat karakter spawn
- **Data**: Nama, Afiliasi, Senjata, Quote (editable di Canvas inspector)
- **Close**: Tombol "Back" atau tap outside panel

---

## 🎬 Demo Video

Demonstrasi fitur-fitur utama tersedia di:
- **YouTube**: [Link demo akan ditambahkan] (production ready video coming soon)
- **Folder lokal**: `/Demo Video/` (jika ada)

---

## 👥 Tim Pengembang (Kelompok 5)

| Peran | Nama |
|------|------|
| **Project Manager** | Kafka Nafisa |
| **UI/UX Designer** | Anisa Aulia |
| **3D Artist, Animator, Sound Designer, QA** | Jizdan Yuflikh R |
| **Developer, Sound Designer** | Nazriel Farras Khairiya Putra Sisworo |

---

## 📝 Lisensi & Disclaimer

### IP Disclaimer
**Star Wars** adalah properti intelektual **Lucasfilm Ltd.** (Disney). Proyek ini adalah **edukasi non-komersial** untuk tujuan pembelajaran Augmented Reality dan tidak bermaksud untuk komersial. Penggunaan aset Star Wars hanya untuk internal project / academic submission.

### Kontribusi & Pengembangan Lanjutan
Tertarik untuk kontribusi? Silakan buat **Pull Request** dengan:
- Deskripsi fitur baru atau bug fix
- Test steps
- Screenshot / video (jika ada perubahan visual)

### Lisensi Kode
Kode sumber tersedia di bawah lisensi **MIT** (see LICENSE file jika ada). Dependency Vuforia Engine mengikuti [Vuforia EULA](https://developer.vuforia.com/terms).

---

## 🔗 Link Penting

- **GitHub Repo**: https://github.com/UnnamedPeople-Chin/Star-Wars-AR-Interactive-Character-Visualizer
- **Vuforia Developer**: https://developer.vuforia.com
- **Unity Docs**: https://docs.unity.com
- **Image Target Images**: `Assets/Image Target/*.jpg`

---

## 📞 Support & Feedback

Menemukan bug atau punya saran? Buka **GitHub Issues** atau hubungi tim melalui:
- Kelompok 5 (academic project contact)
- Repository discussions (jika enabled)

---

**Terakhir diupdate:** 22 Oktober 2026  
**Status**: Production Ready (Founder-Grade Demo Ready)  
**Versi Stabil**: v1.0.0

May the Force Be With You. 🚀✨
