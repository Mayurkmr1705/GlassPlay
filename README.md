# GlassPlay - Android Offline Music Player 🎵

GlassPlay ek modern, offline Android music player application hai jisme **Apple Music jaisa Frosted Glass / Glassmorphism UI** implement kiya gaya hai. Ye Java + XML layouts par based hai.

---

## 🌟 Features

- **Apple Music-Style Glassmorphism UI**:
  - Frosted glass cards, translucent control panels, aur blurred album art background.
  - Smooth slide up/down and fade animations.
- **Offline Music Playback**:
  - Device storage (`MediaStore`) se automatically saare gaane scan aur load karta hai (>30s audio files).
  - Modern storage permission handling (Android 13+ `READ_MEDIA_AUDIO` aur Android 12- `READ_EXTERNAL_STORAGE`).
- **Full Player & Mini Player**:
  - Full-screen player with seekbar, duration timers, current song details, equalizer animation.
  - Persistent bottom mini-player jab gaana play ho raha ho.
- **Playback Controls**:
  - Play, Pause, Next, Previous.
  - **Shuffle Mode**: Randomize queue seamlessly.
  - **Repeat Modes**: Cycle through Repeat None, Repeat All, aur Repeat One Track.
  - Audio focus handling (call aane par pause, disconnect par handle hona).
- **Background Playback & Notification Controls**:
  - Foreground Service (`MusicService`) ke through background playback.
  - Media-style notification with Play/Pause/Next/Prev/Close controls and live album art.
- **Search**:
  - Instant live filter gaano ko Title, Artist, ya Album name se search karne ke liye.

---

## 📁 Project Structure

```
MusicPlayer/
├── build.gradle                   # Root Gradle config
├── settings.gradle                # Module inclusions
├── gradle.properties              # JVM & AndroidX settings
└── app/
    ├── build.gradle               # App dependencies (Glide, Material, Palette, Media)
    └── src/main/
        ├── AndroidManifest.xml    # Permissions, Service, Receiver, Activities
        ├── java/com/glassplay/musicplayer/
        │   ├── GlassPlayApp.java             # Notification channel initialization
        │   ├── adapter/
        │   │   └── SongAdapter.java          # RecyclerView adapter with playing indicator
        │   ├── model/
        │   │   └── Song.java                 # Song data model with duration formatting
        │   ├── receiver/
        │   │   └── NotificationReceiver.java # Media notification actions receiver
        │   ├── service/
        │   │   └── MusicService.java         # Foreground media playback service
        │   ├── ui/
        │   │   ├── MainActivity.java         # Song list, search, mini-player UI
        │   │   └── PlayerActivity.java       # Full-screen glassmorphism player UI
        │   └── utils/
        │       ├── MusicLoader.java          # MediaStore query & search filter logic
        │       └── PlayerManager.java        # Playback controller (MediaPlayer, Shuffle, Repeat)
        └── res/
            ├── anim/                         # Slide & Fade transitions
            ├── drawable/                     # Glass cards, gradients, vectors, seekbar drawables
            ├── layout/                       # activity_main, activity_player, item_song
            └── values/                       # colors, strings, themes, dimens
```

---

## 🚀 How to Run in Android Studio

1. **Android Studio** open karein.
2. **Open** par click karein aur choose karein:
   ```
   C:\Users\talwa\.gemini\antigravity\scratch\MusicPlayer
   ```
3. Gradle sync complete hone dein (dependencies automatically download ho jayengi).
4. Kisi bhi Android Emulator ya physical phone (USB Debugging ON) ko connect karein.
5. **Run** button (`Shift + F10`) dabayein.

---

## 📱 Permissions Used
- `READ_MEDIA_AUDIO` (Android 13+)
- `READ_EXTERNAL_STORAGE` (Android 12 aur usse neeche)
- `FOREGROUND_SERVICE` & `FOREGROUND_SERVICE_MEDIA_PLAYBACK`
- `POST_NOTIFICATIONS`
