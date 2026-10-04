<div align="center">

# Nugget+

**Unlock your device's full potential — with iOS 27 support!**

![Nugget+](nugget+.png)

A customized Nugget build focused on extra features, iOS 27 support, and additional functionality.

</div>

> [!NOTE]
> Please back up your device before using Nugget+. This software can cause unexpected behavior, data loss, or bootloops. Use it at your own risk.

> [!WARNING]
> **I AM NOT RESPONSIBLE FOR DATA LOSS OR BOOTLOOPS. IF SOMETHING GOES WRONG, IT'S YOUR RESPONSIBILITY.**

## About Nugget+

Nugget+ is a customized version of Nugget with additional features and changes aimed at expanding what you can do with your device.

The project is maintained as **Nugget+** and is developed independently while building on the work of the Nugget community.

## Features

<details>
<summary><b>iOS 17.0 - 26.1</b></summary>

### PosterBoard
- Animated wallpapers and descriptors
- Community wallpapers
- Convert videos to wallpapers
- Customize community-made wallpapers using batter files
- Device-specific wallpapers through MercuryPoster
- Documentation for tendies and batter files

### Templates
- Custom operations and file editing
- Batter file support

### Status Bar
- Change carrier name
- Change secondary carrier name
- Enable/disable primary or secondary carriers
- Change Wi-Fi/cellular bar count
- Change battery capacity
- Change battery display detail
- Change time text
- Change date text on iPad
- Change breadcrumb text
- Show numeric Wi-Fi/cellular strength
- Hide or show many status-bar icons

### SpringBoard Options
- Set Lock Screen footnote
- Set Lock Screen idle auto-lock time
- Disable lock after respring
- Disable screen dimming while charging
- Disable low-battery alerts
- Hide AC Power on the Lock Screen
- Show supervision text on the Lock Screen
- Show Dynamic Island in screenshots
- Enable AirPlay support for Stage Manager
- Show the red/green authentication line on the Lock Screen
- Disable the floating tab bar on iPads

### Internal Options
- Build version in the status bar
- Force right-to-left
- Show hidden icons on the Home Screen
- Force Metal HUD Debug
- iMessage Diagnostics
- IDS Diagnostics
- VC Diagnostics
- App Store Debug Gesture
- Notes App Debug Mode
- Show touches with debug information
- Hide respring icon
- Play sound on paste
- Show notifications for system pastes

### Mobile Gestalt
- Enable Dynamic Island on supported devices
- Enable iPadOS on iPhones
- Enable iPhone X gestures on iPhone SEs
- Change device model name
- Enable Boot Chime
- Enable Charge Limit
- Enable Tap to Wake on unsupported devices
- Enable Collision SOS
- Enable Stage Manager
- Disable wallpaper parallax
- Disable region restrictions
- Show Apple Pencil options in Settings
- Show Action Button options in Settings
- Show internal storage information
- Enable the iPhone 16 camera button page in Settings on supported versions
- Enable Always-On Display on supported devices

### Other
- EU Enabler on supported versions
- Feature Flags
- Kiosk Mode
- Liquid Glass/Solarium controls on supported versions
- Lock Screen animation and related options

</details>

<details>
<summary><b>iOS 26.2 - 27.0+</b></summary>

### PosterBoard
- Animated wallpapers and descriptors
- Community wallpapers
- Customize community-made wallpapers using batter files
- Install device-specific wallpapers through MercuryPoster
- Documentation for tendies and batter files

### Templates
- Custom operations and file editing
- Batter file support

### Status Bar
- **iOS 26 and below:** full status-bar override set
  - Change carrier name
  - Change secondary carrier name
  - Enable/disable primary or secondary carriers
  - Change Wi-Fi/cellular bar count
  - Change battery capacity
  - Change battery display detail
  - Change time text
  - Change date text on iPad
  - Change breadcrumb text
  - Show numeric Wi-Fi/cellular strength
  - Hide or show many status-bar icons
- **iOS 27+:**
  - Change carrier name
  - Change secondary carrier name
  - Additional status-bar overrides may not have equivalents because of the new status-bar format
  - iOS 27 functionality should be considered experimental until verified on physical hardware

### SpringBoard Options
- Set Lock Screen footnote
- Set Lock Screen idle auto-lock time
- Disable lock after respring
- Disable screen dimming while charging
- Disable low-battery alerts
- Hide AC Power on the Lock Screen
- Show supervision text on the Lock Screen
- Show Dynamic Island in screenshots
- Enable AirPlay support for Stage Manager
- Show the red/green authentication line on the Lock Screen
- Disable the floating tab bar on iPads

### Internal Options
- Build version in the status bar
- Force right-to-left
- Show hidden icons on the Home Screen
- Force Metal HUD Debug
- iMessage Diagnostics
- IDS Diagnostics
- VC Diagnostics
- App Store Debug Gesture
- Notes App Debug Mode
- Show touches with debug information
- Hide respring icon
- Play sound on paste
- Show notifications for system pastes

### Liquid Glass
- Ignore Liquid Glass app build check
- Force Solarium fallback where supported

### Disable Daemons
- OTAd
- UsageTrackingAgent
- Game Center
- Screen Time Agent
- Logs, dumps, and crash reports
- ATWAKEUP
- Tipsd
- VPN
- Chinese WLAN service
- HealthKit
- AirPrint
- Assistive Touch
- iCloud
- Internet Tethering / Personal Hotspot
- PassBook
- Spotlight

</details>

## Requirements

<details>
<summary><b>Windows</b></summary>

- [Apple Devices](https://apps.microsoft.com/detail/9np83lwlpz9k) from the Microsoft Store **or**
- [iTunes](https://support.apple.com/en-us/106372) from Apple

</details>

<details>
<summary><b>Linux</b></summary>

- [usbmuxd](https://github.com/libimobiledevice/usbmuxd)
- [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice)

</details>

<details>
<summary><b>Running Python</b></summary>

- [pymobiledevice3](https://github.com/doronz88/pymobiledevice3)
- [PySide6](https://doc.qt.io/qtforpython-6/)
- [ffmpeg-python](https://pypi.org/project/ffmpeg-python/) for video wallpapers
- [opencv-python](https://pypi.org/project/opencv-python/) for video wallpapers
- Python 3.10 or newer

All pinned dependencies are in `requirements.txt`.

</details>

## Running the Python Program

It is recommended to use a virtual environment.

```bash
python3 -m venv .env
```

### macOS / Linux

```bash
source .env/bin/activate
```

### Windows

```bat
.env\Scripts\activate.bat
```

### Install and run

```bash
pip3 install -r requirements.txt
python3 main_app.py
```

Depending on your system, use either `python`/`pip` or `python3`/`pip3`.

## Building

Compile `mainwindow.ui`:

```bash
pyside6-uic --from-imports src/qt/mainwindow.ui -o src/qt/mainwindow_ui.py
```

Compile resources:

```bash
pyside6-rcc src/qt/resources.qrc -o src/qt/resources_rc.py
```

Create/update translations:

```bash
pyside6-lupdate main_app.py src/gui/main_window.py src/gui/pages/page.py src/gui/pages/pages_list.py src/gui/pages/main/*.py src/gui/pages/tools/*.py src/gui/dialogs/*.py src/gui/ios/*.py src/qt/mainwindow.ui src/devicemanagement/device_manager.py src/exceptions/*.py src/tweaks/*.py src/tweaks/posterboard/*.py src/tweaks/posterboard/template_options/*.py src/tweaks/status_bar/*.py src/controllers/*.py -ts src/qt/translations/Nugget_{language code}.ts

pyside6-lrelease src/qt/translations/Nugget_{language code}.ts -qm src/qt/translations/Nugget_{language code}.qm
```

Build the application:

```bash
python3 compile.py
```

## iOS 27 Support

Nugget+ includes experimental iOS 27 support.

Some options from older iOS versions do not have direct equivalents in iOS 27 because Apple changed parts of the system, including the status-bar format.

**Use iOS 27 features at your own risk.**

## Forks & Project Lineage

Nugget+ is part of the broader Nugget project ecosystem. The following projects are referenced as forks/related upstream projects:

- **[GoldenNugget](https://github.com/GoldenNugget-Team/GoldenNugget)** — an iOS 27-focused Nugget fork with additional changes and features.
- **[Nugget](https://github.com/leminlimez/Nugget)** — the original Nugget project that Nugget+ builds upon.

Nugget+ is maintained separately at:

**[nugget-plus/nugget-plus](https://github.com/nugget-plus/nugget-plus)**

## Contributing

Contributions, bug fixes, testing, documentation, and feature improvements are welcome.

### Contributor

- **[1lsgw](https://github.com/1lsgw)** — Nugget+ contributor and maintainer

## Credits

Nugget+ would not be possible without the work of the wider Nugget community and its upstream projects.

Special thanks to:

- **[LeminLimez](https://github.com/leminlimez)** — creator of Nugget
- **[GoldenNugget-Team](https://github.com/GoldenNugget-Team/GoldenNugget)** — GoldenNugget project
- **[pymobiledevice3](https://github.com/doronz88/pymobiledevice3)** — device communication and restore functionality
- **[PySide6](https://doc.qt.io/qtforpython-6/)** — GUI framework
- Everyone who has contributed code, testing, translations, documentation, and ideas to the Nugget ecosystem

## Disclaimer

Nugget+ is provided as-is.

You are responsible for your device and your data.

**Always back up your device before using Nugget+.**

---

<div align="center">

**Nugget+ — customize your device, your way.**

</div>
