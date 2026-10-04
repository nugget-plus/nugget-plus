<div align="center">

# Nugget+

**Unlock your device's full potential — with iOS 27 support!**

![Nugget+](nugget+.png)

</div>

Customize your device with animated wallpapers, status-bar tweaks, SpringBoard options, internal settings, daemon controls, and more.

> [!NOTE]
> Please back up your data before using this project. Nugget+ may cause unforeseen problems, including data loss or bootloops. Use it at your own risk.

> [!WARNING]
> **I AM NOT RESPONSIBLE FOR DATA LOSS OR BOOTLOOPS. IF SOMETHING GOES WRONG, IT'S YOUR RESPONSIBILITY.**

## Discord Server

Need support or want to talk about the project?

[Join the Nugget+ Discord Server](https://discord.gg/Rm6r4zeE3y)

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
- Change the number of Wi-Fi/cellular bars
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
- Enable the iPhone 16 camera button page in Settings on supported iOS versions
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
  - Additional status-bar overrides may not be available because of the new status-bar format
  - iOS 27 status-bar functionality should be considered experimental until verified on physical hardware

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
- [iTunes](https://support.apple.com/en-us/106372) from Apple's website

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

It is highly recommended to use a virtual environment.

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

Depending on your system configuration, use either `python`/`pip` or `python3`/`pip3`.

## Building

Compile `mainwindow.ui`:

```bash
pyside6-uic --from-imports src/qt/mainwindow.ui -o src/qt/mainwindow_ui.py
```

Compile the resources:

```bash
pyside6-rcc src/qt/resources.qrc -o src/qt/resources_rc.py
```

Create/update translations:

```bash
pyside6-lupdate main_app.py src/gui/main_window.py src/gui/pages/page.py src/gui/pages/pages_list.py src/gui/pages/main/*.py src/gui/pages/tools/*.py src/gui/dialogs/*.py src/gui/ios/*.py src/qt/mainwindow.ui src/devicemanagement/device_manager.py src/exceptions/*.py src/tweaks/*.py src/tweaks/posterboard/*.py src/tweaks/posterboard/template_options/*.py src/tweaks/status_bar/*.py src/controllers/*.py -ts src/qt/translations/Nugget_{language code}.ts

pyside6-lrelease src/qt/translations/Nugget_{language code}.ts -qm src/qt/translations/Nugget_{language code}.qm
```

Build the application with:

```bash
python3 compile.py
```

## iOS 27 Support

Nugget+ includes experimental support for iOS 27.

Some older tweaks depended on functionality that changed in iOS 27, so not every option from earlier iOS releases has an equivalent on iOS 27.

**Use iOS 27 functionality at your own risk.**

## Important Notes

- Always make a backup before using Nugget+.
- Some tweaks can cause instability or unexpected behavior.
- Features can vary depending on the iOS version and device.
- Do not assume that an option working in a simulator has been verified on physical hardware.
- Do not use potentially dangerous tweaks unless you understand their effects.

## Contributing

Contributions, fixes, translations, and feature improvements are welcome.

Please open a pull request with a clear description of your changes.

## Credits

Nugget+ builds on the work of the original Nugget project and the contributors who made its features possible.

- [LeminLimez](https://github.com/leminlimez) — original Nugget
- [PosterRestore](https://discord.gg/gWtzTVhMvh) — PosterBoard support
- [pymobiledevice3](https://github.com/doronz88/pymobiledevice3) — device communication and restore algorithms
- [PySide6](https://doc.qt.io/qtforpython-6/) — GUI framework
- [iTechExpert](https://twitter.com/iTechExpert21) — SpringBoard/Internal Options
- [Mikasa-san](https://github.com/Mikasa-san) — Quiet Daemon
- [Wind0ws11Aero](https://github.com/Wind0ws11Aero) — development contributions
- And everyone who has contributed code, testing, translations, documentation, and ideas.

## Disclaimer

Nugget+ is provided as-is. You are responsible for your device and your data.

**Back up your device before using Nugget+.**

---

<div align="center">

**Nugget+ — customize your device, your way.**

</div>
