# 🚀 Flutter Installation Guide (All Platforms)

This repository documents **standard, beginner-safe Flutter installation methods** for:

* Windows (Chocolatey + manual backup)
* macOS (Homebrew)
* Linux (APT / manual)

It also includes **common errors and fixes** exactly like real-world setup issues.

---

## 📁 Repository Structure

```
flutter-install-guide/
├── windows/
│   ├── chocolatey.md
│   ├── manual-backup.md
│   └── common-errors.md
├── macos/
│   ├── homebrew.md
│   └── common-errors.md
├── linux/
│   ├── apt.md
│   ├── snap.md
│   └── common-errors.md
└── README.md
```

---

# 🪟 Windows Installation

## Method 1: Chocolatey (Recommended)

### 1. Install Chocolatey

Run **PowerShell as Administrator**:

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force;
[System.Net.ServicePointManager]::SecurityProtocol = 3072;
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Verify:

```powershell
choco --version
```

---

### 2. Install Flutter

```powershell
choco install flutter -y
```

Refresh PATH:

```powershell
refreshenv
```

Verify:

```powershell
flutter --version
```

---

### 3. Install Android Studio

```powershell
choco install androidstudio -y
```

Inside Android Studio:

* Install Android SDK
* Install Platform Tools
* Install Emulator
* Create one AVD

---

### 4. Accept Licenses

```powershell
flutter doctor --android-licenses
```

---

### 5. Verify

```powershell
flutter doctor
```

---

## Method 2: Manual Backup (If Chocolatey fails)

### 1. Download Flutter SDK

* [https://flutter.dev](https://flutter.dev)
* Download **Windows ZIP**

Extract to:

```
C:\flutter
```

---

### 2. Add Flutter to PATH

Add this to **User PATH**:

```
C:\flutter\bin
```

Restart terminal.

Verify:

```powershell
flutter --version
```

---

# 🍎 macOS Installation

## Method: Homebrew (Standard)

### 1. Install Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Verify:

```bash
brew --version
```

---

### 2. Install Flutter

```bash
brew install flutter
```

Verify:

```bash
flutter doctor
```

---

### 3. Install Android Studio

```bash
brew install --cask android-studio
```

Install SDK + Emulator inside Android Studio.

---

### 4. Install Xcode (Required for iOS)

```bash
xcode-select --install
sudo xcodebuild -license accept
```

---

# 🐧 Linux Installation

## Method 1: APT (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install curl git unzip xz-utils zip libglu1-mesa
```

Download Flutter:

```bash
cd ~
wget https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_3.38.5-stable.tar.xz
tar xf flutter_linux_3.38.5-stable.tar.xz
```

Add to PATH:

```bash
echo 'export PATH="$PATH:$HOME/flutter/bin"' >> ~/.bashrc
source ~/.bashrc
```

Verify:

```bash
flutter doctor
```

---

## Method 2: Snap (Simplest)

```bash
sudo snap install flutter --classic
```

---

# ❌ Common Errors & Fixes

## flutter: command not found

**Cause:** PATH not refreshed

**Fix:**

* Restart terminal
* Or manually add Flutter bin to PATH

---

## Android SDK not found

**Cause:** Android Studio SDK not installed

**Fix:**

* Open Android Studio
* SDK Manager → Install SDK + Platform Tools

---

## Android licenses not accepted

```bash
flutter doctor --android-licenses
```

Press `y` for all.

---

## Wrong SDK / Build Tools Version

**Fix:**

* Open SDK Manager
* Install required API level shown in `flutter doctor`

---

# ✅ Final Verification (All OS)

```bash
flutter doctor
```

Expected:

```
[✓] Flutter
[✓] Android toolchain
[✓] Chrome (optional)
[✓] Connected device
```

---

## 🎯 Recommended Editor

* VS Code
* Extensions:

  * Flutter
  * Dart

---

## 🏁 You're Ready

```bash
flutter create my_app
cd my_app
flutter run
```

Happy Fluttering 🚀
