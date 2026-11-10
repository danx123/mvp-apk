# MVP — Macan Video Player

<p align="center">
  <img src="https://img.shields.io/badge/Release-v1.2.0-FF9E0B?style=for-the-badge" alt="Release Version" />
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/Architecture-Jetpack%20Compose-4285F4?style=for-the-badge" alt="Jetpack Compose" />
  <img src="https://img.shields.io/badge/Engine-Media3%20ExoPlayer-00E5FF?style=for-the-badge" alt="Media3 ExoPlayer" />
</p>


A fast, clean, gesture-driven video player for Android. MVP uses native hardware decoding through Android's MediaCodec (via Media3 / ExoPlayer) for smooth playback, wrapped in a dark black-and-orange interface.

---
## Screenshot

<img width="720" height="1600" alt="Screenshot_2026-11-09-19-05-53-38" src="https://github.com/user-attachments/assets/ceabee3f-72c7-49d6-bd2d-0a491c034efc" />

---

## Features

### Playback
- **Hardware decoding** through MediaCodec, with automatic decoder fallback for compatibility
- **Playback speed** from 0.5x to 2.0x
- **Aspect ratio modes:** Fit, Zoom, Fill, 16:9 and 4:3
- **Orientation toggle** between portrait and landscape from the player
- **Resume session:** pick up where you left off, with a quick-resume card on the home screen
- **Screen stays on** during playback
- **Auto-pause** when headphones are unplugged

### Gesture controls
- **Swipe up/down on the left half** to adjust brightness
- **Swipe up/down on the right half** to adjust volume
- **Double-tap left or right** to rewind or fast-forward 10 seconds
- **Tap** to show or hide controls
- **Screen lock** to prevent accidental touches

### Subtitles
- Supports embedded subtitle tracks
- Load external **.srt** and **.vtt** files
- Custom subtitle style: orange text, semi-transparent background and a black outline for readability

### Library
- Automatically scans videos on your device and groups them by folder
- **Grid or list view** for folders and videos
- **Search** videos by name
- **8 sort options:** name, date, size and duration (ascending or descending)
- **Select any folder** manually, or **open a single video file** directly
- Video thumbnails with caching for fast browsing
- Open videos straight from file managers and browsers — MVP registers itself as a handler for video files

### Interface
- Dark theme with a signature fiery-orange accent
- **Languages:** English, Bahasa Indonesia, or follow the system language

---

## Installation

1. Download the latest `MVP` APK file.
2. Open the APK on your Android device.
3. If prompted, allow installation from your browser or file manager (**Install unknown apps**).
4. Tap **Install**, then open **MVP**.

> Installing a newer version over an existing one keeps your settings and resume history, as long as the APK is signed with the same key.

## Permissions

| Permission | Why it is needed |
|---|---|
| Video access (`READ_MEDIA_VIDEO`, or `READ_EXTERNAL_STORAGE` on Android 12 and below) | To scan and list the videos on your device |
| Wake lock | To keep playback running smoothly with the screen on |
| Notifications / foreground service | Media playback support |

If you prefer not to grant full video access, you can still use **Select Folder** or **Open File** to play videos through Android's file picker.

## Supported Formats

MVP plays what your device's hardware decoders support. Common containers such as MP4, MKV, WebM, AVI and MOV are recognized. Actual codec support (H.264, HEVC, VP9, AV1, etc.) depends on your phone's chipset.

## Quick Start

1. Open MVP and grant video access.
2. Tap a folder, then tap a video to play.
3. Use gestures or the on-screen controls during playback.
4. Next time you open the app, tap the **Resume Session** card to continue.

## Troubleshooting

- **No videos appear:** make sure video access is granted, then tap the refresh button. You can also use **Select Folder** to browse manually.
- **A video has no sound or picture:** the codec may not be supported by your device's hardware decoder.
- **Subtitles not showing:** open the subtitle menu in the player and make sure a track is selected, or load an external `.srt` / `.vtt` file.

## Feedback

Found a bug or have a suggestion? Please include your device model, Android version and the app version when reporting.

---

© Macan Angkasa. All rights reserved.
