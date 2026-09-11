# Windows Fader Bridge for EUCON User Guide

[简体中文](USER_GUIDE.zh-CN.md) ・ [日本語](USER_GUIDE.ja.md) ・ [Home](../README.md)

## What it does

The app presents the Windows audio mixer as a dedicated EUCON application. Use an Avid S3, another compatible surface, or Avid Control to operate the main output, input devices, and active Windows applications.

It does not replace EuControl or modify your audio driver. Volume, pan, mute, solo, selection, meters, and motor-fader feedback are synchronized in real time.

![Windows Fader Bridge overview](images/overview.png)

## Requirements

- Windows 11, 64-bit.
- Avid EuControl / EUCON Workstation 2026.4 installed and working.
- A compatible surface connected in EuControl, or a tablet running Avid Control.

## Install

1. Download the file ending in `Setup-x64.exe` from [Releases](https://github.com/lindelea/windows-fader-bridge-eucon/releases/latest).
2. Quit any portable copy you previously started, run the installer, and follow the prompts.
3. The installer also prepares the required Microsoft Visual C++ Runtime.
4. Open **Windows Fader Bridge for EUCON** from the Start menu.

The project does not currently have a paid Windows code-signing certificate, so Windows may show “Unknown publisher.” Download only from this repository and compare the file with the SHA-256 value on the release page if needed.

## First connection

1. Make sure EuControl is running and your surface is online.
2. Start the bridge. It is ready when the overview reports that the controller is connected.
3. If EUCON is focused on another application, bring this window forward once or press `Ctrl+Alt+Shift+W`.
4. For regular switching between Cubase, Windows audio, and UAD Console, assign the bridge's **Windows EUCON** and **UAD EUCON** commands to EuControl Soft Keys.

![Confirm the application in EuControl](images/eucontrol-applications.png)

![Assign bridge-switching commands to EuControl Soft Keys](images/eucontrol-commands.png)

Startup order is not critical. If Windows Audio or EUCON is not ready during sign-in, the bridge waits and reconnects automatically.

## Everyday controls

- Fader: channel volume; Master follows the Windows default output.
- Pan encoder: pan or stereo balance; press to return to center.
- Mute / Solo: control and display the actual Windows state.
- Bank: move through groups of online channels.
- Meter: live Windows audio level, not a decorative animation.
- Click a row in the Overview page to select that channel.

Closed applications leave the online list and return under their stable identity when active again. A channel-list change is deferred while a fader is touched so a gesture cannot jump to another application.

## Settings and background operation

Settings provide English/Chinese language selection, launch at Windows sign-in, close to tray, the global summon shortcut, and whether the window should immediately return to the background after EUCON recognizes it. The default shortcut is `Ctrl+Alt+Shift+W`; you may record another combination, but avoid conflicts with other global shortcuts.

Closing the window normally leaves the bridge in the notification area. Right-click its tray icon to show, restart, or fully quit it.

## Troubleshooting

**The surface cannot see the bridge:** confirm that EuControl and the bridge are running, check the Applications page in EuControl, then use the global summon shortcut.

**An application has no channel:** it must first create a Windows audio session; playing audio once is usually enough.

**A fader rebounds or does not match:** make sure another utility is not controlling the same Windows session. Restart the bridge from its tray menu. If it continues, open the log folder from Settings and attach the newest log to a report.

**Uninstall:** open Windows Settings → Apps → Installed apps and uninstall the bridge. Personal settings are retained for reinstall; delete the corresponding folder under `%LOCALAPPDATA%` only if you also want to remove them.

## Report a problem

Open a [GitHub issue](https://github.com/lindelea/windows-fader-bridge-eucon/issues) with your Windows, EuControl and surface versions, reproduction steps, and observed result. Logs may contain local application and device names, so review them before uploading.
