# MVP — Macan Video Player

<p align="center">
  <img src="https://img.shields.io/badge/Release-v1.4.6-FF9E0B?style=for-the-badge" alt="Release Version" />
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/Architecture-Jetpack%20Compose-4285F4?style=for-the-badge" alt="Jetpack Compose" />
  <img src="https://img.shields.io/badge/Engine-Media3%20ExoPlayer-00E5FF?style=for-the-badge" alt="Media3 ExoPlayer" />
</p>


A fast, clean, gesture-driven video player for Android. MVP is a dual-engine player: it uses native hardware decoding through Android's MediaCodec (via Media3 / ExoPlayer) for smooth, battery-friendly playback, and can optionally add an FFmpeg software decoder as a second engine for wider format support. Everything is wrapped in a dark black-and-orange interface.

---
## Screenshot

<img width="1452" height="1600" alt="mvp-sc128" src="https://github.com/user-attachments/assets/64135c87-5ac3-4452-a266-38ee3f567179" />


---

## Features

### Playback
- **Hardware decoding** through MediaCodec, with automatic decoder fallback for compatibility
- **Second engine (FFmpeg)** — optional software decoder for formats your hardware can't handle. In hybrid mode, MVP tries the hardware decoder first and automatically retries with FFmpeg if playback fails
- **Playback speed** from 0.5x to 2.0x
- **Aspect ratio modes:** Fit, Zoom, Fill, 16:9 and 4:3
- **Orientation toggle** between portrait and landscape from the player
- **Previous / Next** buttons, with automatic advance to the next video in the folder when one ends
- **Resume session:** pick up where you left off, with a quick-resume card on the home screen and per-video resume positions
- **Background audio play:** keep the audio going when MVP is minimized (optional, off by default)
- **Screen stays on** during playback
- **Auto-pause** when headphones are unplugged

### Gesture controls
- **Swipe up/down on the left half** to adjust brightness
- **Swipe up/down on the right half** to adjust volume
- **Double-tap left or right** to rewind or fast-forward (5, 10, 15 or 30 seconds)
- **Tap** to show or hide controls
- **On-screen HUD** showing brightness and volume levels
- **Screen lock** to prevent accidental touches

### Audio equalizer
- **5-band hardware equalizer** (60 Hz, 230 Hz, 910 Hz, 3.6 kHz, 14 kHz) with ±10 dB per band
- **Presets:** Normal, Bass Boost, Rock, Pop, Jazz, Classical, Vocal, plus Custom
- Reset to flat with one tap; settings are remembered between sessions

### Subtitles
- Supports embedded subtitle tracks
- Load external **.srt** and **.vtt** files
- Custom subtitle style: orange text, semi-transparent background and a black outline for readability

### Library
- Automatically scans videos on your device and groups them by folder
- **Grid or list view** for folders and videos
- **Search** videos by name
- **8 sort options:** name, date, size and duration (ascending or descending)
- **"NEW" badges** on videos you haven't opened yet, with a new-video count on each folder
- **Select any folder** manually, or **open a single video file** directly
- **File actions** (long-press): play, cut, copy, paste, rename, share and delete videos; folders can be cut, copied, pasted, renamed and deleted
- **Smart thumbnails:** multi-tier extraction with memory and disk caching, including a MediaCodec fallback for AV1 and VP9 videos that the system can't thumbnail
- **Reliable metadata:** duration and resolution are recovered even when MediaStore doesn't provide them
- Open videos straight from file managers, galleries and browsers — MVP registers itself as a handler for video files and accepts shared videos

### Settings & interface
- Dark theme with a signature fiery-orange accent
- **Languages:** English, Bahasa Indonesia, or follow the system language
- Configurable options: gesture overlay, HUD indicator, double-tap seek and duration, auto-resume, controls auto-hide timeout (3, 4, 6 or 8 seconds), hardware acceleration, FFmpeg second engine, background audio play and exit confirmation
- Settings are available from both the library and the player

---

## Installation

1. Download the latest `MVP` APK file.
2. Open the APK on your Android device.
3. If prompted, allow installation from your browser or file manager (**Install unknown apps**).
4. Tap **Install**, then open **MVP**.

> Installing a newer version over an existing one keeps your settings and resume history, as long as the APK is signed with the same key.

Requires **Android 7.0 (API 24)** or newer.

## Permissions

| Permission | Why it is needed |
|---|---|
| Video access (`READ_MEDIA_VIDEO` on Android 13+, `READ_EXTERNAL_STORAGE` on Android 12 and below) | To scan and list the videos on your device |
| Selected video access (`READ_MEDIA_VISUAL_USER_SELECTED`) | Lets you grant access to only some videos on Android 14+ |
| Storage write (`WRITE_EXTERNAL_STORAGE`, Android 10 and below) | To copy, rename and delete videos on older devices |
| Wake lock | To keep playback running smoothly with the screen on |
| Notifications / foreground service | Media playback support |
| Modify audio settings | To apply the audio equalizer |

On newer Android versions, deleting a video shows a system confirmation dialog before the file is removed.

If you prefer not to grant full video access, you can still use **Select Folder** or **Open File** to play videos through Android's file picker.

## Supported Formats

MVP plays what your device's hardware decoders support. Common containers such as MP4, MKV, WebM, AVI and MOV are recognized. Actual codec support (H.264, HEVC, VP9, AV1, etc.) depends on your phone's chipset.

Turn on **Second Engine (FFmpeg)** in Settings to widen support through software decoding for formats such as MKV, AVI, FLV, AV1, HEVC, AC3 and DTS. Software decoding uses more battery than hardware decoding, so it is off by default.

## Quick Start

1. Open MVP and grant video access.
2. Tap a folder, then tap a video to play.
3. Use gestures or the on-screen controls during playback.
4. Long-press a video or folder for file actions.
5. Next time you open the app, tap the **Resume Session** card to continue.

## Troubleshooting

- **No videos appear:** make sure video access is granted, then tap the refresh button. You can also use **Select Folder** to browse manually.
- **A video has no sound or picture:** the codec may not be supported by your device's hardware decoder. Enable **Second Engine (FFmpeg)** in Settings and try again.
- **Playback is choppy with FFmpeg:** software decoding of high-resolution video can be demanding. Keep Hardware Acceleration on so MVP uses your chipset when it can.
- **Subtitles not showing:** open the subtitle menu in the player and make sure a track is selected, or load an external `.srt` / `.vtt` file.
- **A video can't be deleted:** confirm the system permission prompt when it appears, and check that video access is granted.
- **Equalizer has no effect:** make sure it is switched on in Settings → Audio Equalizer.

## Feedback

Found a bug or have a suggestion? Please include your device model, Android version and the app version when reporting.

---

© Macan Angkasa. All rights reserved.
