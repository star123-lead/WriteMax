<div align="center">

<img src="app/src/main/res/drawable/writemax_logo.png" alt="WriteMax Logo" width="120" height="120" />

# ⌨️ WriteMax

**A Smart Android Keyboard Built with Jetpack Compose**

![Android](https://img.shields.io/badge/Android-8.0%2B-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-2.0-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-UI-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white)
![Target SDK](https://img.shields.io/badge/Target%20SDK-36%20(Android%2016)-blue?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-1.0-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

> A custom Android IME (Input Method Editor) keyboard application built using modern Android development practices — Jetpack Compose, Kotlin, and the latest Android SDK 36.

[📥 Download APK](#download) · [🚀 Features](#features) · [🛠️ Setup](#setup) · [📸 Screenshots](#screenshots) · [🤝 Contributing](#contributing)

</div>

---

## 📖 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Screenshots](#screenshots)
- [Download](#download)
- [Setup & Installation](#setup)
- [How to Enable the Keyboard](#how-to-enable)
- [Project Structure](#project-structure)
- [Permissions](#permissions)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [Author](#author)
- [License](#license)

---

## 📌 About

**WriteMax** is a fully custom Android keyboard (IME) app developed using **Jetpack Compose** and **Kotlin**. It is designed to provide a smooth, minimal, and modern typing experience on Android devices. This project was built to explore Android's `InputMethodService` API combined with the power of modern Compose-based UI rendering.

Unlike most keyboard apps that rely on legacy XML-based views, WriteMax uses a **Compose-first approach** for keyboard rendering — making it highly customizable and easy to extend.

---

## ✨ Features

- 🎨 **Modern UI** — Built 100% with Jetpack Compose
- ⌨️ **Custom IME** — Full `InputMethodService` implementation via `WriteMaxKeyboardService`
- 🚀 **Fast & Lightweight** — Optimized with `extractNativeLibs=false` and Baseline Profiles
- 📱 **Wide Compatibility** — Supports Android 8.0 (API 26) and above
- 🌙 **Dark/Light Theme Ready** — Theme-aware architecture
- 😀 **Emoji Support** — Integrated via `androidx.emoji2` for modern emoji rendering
- 🔒 **Privacy First** — No internet permission, no data collection
- 🪟 **Foldable Support** — Window extension libraries included for foldable/multi-window devices

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Kotlin** | Primary programming language |
| **Jetpack Compose** | Modern declarative UI toolkit |
| **InputMethodService** | Android keyboard (IME) core API |
| **AndroidX Lifecycle** | Lifecycle-aware components |
| **AndroidX Startup** | App startup optimization |
| **AndroidX Emoji2** | Modern emoji rendering |
| **Baseline Profiles** | App performance optimization |
| **Window Extensions** | Foldable device support |

---

## 🏗️ Architecture

```
WriteMax
├── MainActivity              → App entry point & keyboard setup guide
├── WriteMaxKeyboardService   → Core IME Service (keyboard logic & rendering)
└── Jetpack Compose UI        → All keyboard UI built with @Composable functions
```

The keyboard runs as an Android **Service** (`WriteMaxKeyboardService`) registered with `android.view.InputMethod` intent filter. The UI is rendered using Jetpack Compose inside the `InputMethodService` window.

---

## 📸 Screenshots

> *(Add your screenshots here after taking them from a real device or emulator)*

| Home Screen | Keyboard Active | Settings |
|:-----------:|:---------------:|:--------:|
| ![home](screenshots/home.png) | ![keyboard](screenshots/keyboard.png) | ![settings](screenshots/settings.png) |

---

## 📥 Download

| Build | Link |
|-------|------|
| **Debug APK (v1.0)** | [⬇️ Download app-debug.apk](releases/app-debug.apk) |
| **Release APK** | *Coming soon* |

> ⚠️ **Note:** This is a debug build. For production use, build a signed release APK.

---

## ⚙️ Setup

### Prerequisites

Make sure you have the following installed:

- [Android Studio Hedgehog or later](https://developer.android.com/studio)
- JDK 17+
- Android SDK with API 36 installed
- A physical Android device or emulator running Android 8.0+

### Clone the Repository

```bash
git clone https://github.com/star123-lead/writemax.git
cd writemax
```

### Open in Android Studio

1. Open **Android Studio**
2. Click **File → Open**
3. Select the cloned `writemax` folder
4. Let Gradle sync finish
5. Connect your Android device or start an emulator

### Build & Run

```bash
# Debug build
./gradlew assembleDebug

# Install directly to connected device
./gradlew installDebug
```

Or just click the ▶️ **Run** button in Android Studio.

---

## 🔑 How to Enable the Keyboard

After installing the app, follow these steps to activate WriteMax as your keyboard:

1. Open **Settings** on your Android phone
2. Go to **General Management → Keyboard list and default** (may vary by device)
3. Tap **On-screen keyboard** → **Manage keyboards**
4. Enable **WriteMax** from the list
5. Tap **WriteMax** to set it as the default keyboard
6. Open any text field — WriteMax will now appear!

> 💡 The **WriteMax app** also includes a guide screen (`MainActivity`) that walks you through this setup.

---

## 📁 Project Structure

```
writemax/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/writemax/
│   │   │   │   ├── MainActivity.kt           ← Launch screen
│   │   │   │   └── WriteMaxKeyboardService.kt ← IME Service
│   │   │   ├── res/
│   │   │   │   ├── drawable/
│   │   │   │   │   └── writemax_logo.png
│   │   │   │   └── xml/
│   │   │   │       └── method.xml            ← IME metadata
│   │   │   └── AndroidManifest.xml
│   └── build.gradle.kts
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

---

## 🔐 Permissions

WriteMax requests **minimal permissions** to respect user privacy:

| Permission | Purpose |
|---|---|
| `BIND_INPUT_METHOD` | Required by Android to register as a keyboard (IME) |
| `DYNAMIC_RECEIVER_NOT_EXPORTED_PERMISSION` | Internal broadcast security (auto-generated by AndroidX) |

> ✅ **No internet, camera, microphone, or contacts permissions.** Your typing data never leaves your device.

---

## 🗺️ Roadmap

- [x] Basic IME keyboard implementation
- [x] Jetpack Compose UI
- [x] Emoji support
- [x] Foldable device compatibility
- [ ] Multiple language support
- [ ] Custom themes (Dark / AMOLED / Light)
- [ ] Swipe-to-type (gesture typing)
- [ ] Clipboard manager integration
- [ ] One-handed keyboard mode
- [ ] Play Store release (signed APK)

---

## 🤝 Contributing

Contributions are welcome! Here's how:

```bash
# 1. Fork this repo
# 2. Create your feature branch
git checkout -b feature/your-feature-name

# 3. Commit your changes
git commit -m "feat: add your feature"

# 4. Push to your branch
git push origin feature/your-feature-name

# 5. Open a Pull Request
```

Please follow [conventional commits](https://www.conventionalcommits.org/) for commit messages.

---

## 👨‍💻 Author

**Thangamani Palanivel (Star)**

- 🌐 Portfolio: [starerr.com](https://starerr.com)
- 💼 LinkedIn: [thangamani-p](https://www.linkedin.com/in/thangamani-p-b694953ba)
- 🐙 GitHub: [@star123-lead](https://github.com/star123-lead)
- 📧 Email: ptm9541@gmail.com

---

## 📄 License

```
MIT License

Copyright (c) 2025 Thangamani Palanivel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

<div align="center">

Made with ❤️ in Namakkal, Tamil Nadu 🇮🇳

⭐ **Star this repo if you found it useful!**

</div>
