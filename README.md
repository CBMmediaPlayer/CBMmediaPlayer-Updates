# 🎬 CBM Media Player Pro

A modern macOS media player focused on premium playback quality, immersive fullscreen viewing, advanced subtitle handling, and unified casting.

<p align="center">
  <img src="https://img.shields.io/badge/macOS-14%2B-black?style=for-the-badge&logo=apple" />
  <img src="https://img.shields.io/badge/Apple%20Silicon-Supported-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Intel%20Macs-Supported-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/SwiftUI-Powered-orange?style=for-the-badge" />
</p>

---

**CBM Media Player** is a native macOS media player built with SwiftUI, Metal, FFmpeg, and VideoToolbox. It is designed for large local movie libraries, high-bitrate 4K/HDR playback, rich subtitle control, resume history, advanced playlist workflows, casting, and a polished full-screen viewing experience.

## ✨ Highlights

- 🎞️ **Wide format playback** with FFmpeg demuxing and custom playback engine
- ⚡ **Hardware decoding** with VideoToolbox where supported
- 🖥️ **Metal video renderer** with HDR/EDR output, Lanczos scaling, tone handling, and picture tuning
- 🧭 **Library mode** with grid/list views, favorites, search, sort, selection, and bulk delete
- ▶️ **Continue Watching + Resume Hub** for quickly returning to unfinished videos
- 📊 **Watch statistics** with optional recording and reset controls
- 🖼️ **Smart thumbnails** using video-frame extraction, large-file fallback extraction, and optional TMDB artwork
- 🔎 **Seek preview thumbnails** while hovering/scrubbing the timeline
- 💬 **Advanced subtitles** with embedded tracks, external files, secondary subtitles, sync, style, size, color, and position controls
- 🌐 **OpenSubtitles search/download** support
- 🎛️ **Fine Tune panel** for playback speed, sync, picture, audio EQ, and filters
- 📺 **Cast support** for AirPlay, Chromecast, DLNA, Roku-style targets, and local HTTP streaming workflows
- 🪟 **Mini Player Pro** and Picture-in-Picture support
- 📸 **Snapshots and capture settings**
- 🎨 **Premium themes** with dark/light system-follow option
- 🧹 **Clear app data/cache** controls for thumbnails, metadata, resume history, bookmarks, statistics, and settings
- 🔄 **Sparkle updater** integration

## 🧩 Supported Formats

### Video

`mp4`, `m4v`, `mkv`, `avi`, `wmv`, `mov`, `flv`, `webm`, `mpg`, `mpeg`, `m2ts`, `mts`, `ts`, `vob`, `3gp`, `3g2`, `ogv`, `divx`, `asf`, `f4v`, `rmvb`, `rm`, `y4m`, `mxf`, `dv`, `nut`, `m2v`, `h264`, `h265`, `hevc`, `av1`, `ivf`

### Audio

`mp3`, `flac`, `aac`, `ogg`, `wma`, `wav`, `m4a`, `opus`, `aiff`, `ac3`, `dts`, `ape`, `mka`, `wv`, `tta`, `spx`, `caf`, `alac`

### Subtitles

`srt`, `ass`, `ssa`, `vtt`, `sub`, `idx`, `smi`, `lrc`

## 🏛️ Main Features

### 🎥 Playback

- Native macOS player window with custom controls
- Play/pause, previous/next, forward/back 10 seconds
- Smooth seek bar with chapter markers and bookmark markers
- Speed control from slow playback to fast scan
- Aspect ratio and transform controls
- Loop modes and A-B repeat
- Fullscreen playback with custom controls
- Audio-only playback mode with artwork/visual interface

### 🖼️ Video Quality

- Metal rendering pipeline
- HDR/EDR display support
- Lanczos scaling pipeline
- Hardware acceleration toggle
- Brightness, contrast, saturation, hue, gamma, and sharpness tuning
- Denoise, deband, and deinterlace filter controls
- Large-file thumbnail extraction fallback for high-bitrate media

### 🔊 Audio

- Multi-track audio selection
- Volume up to 200%
- Mute/unmute controls
- Audio delay correction
- Preferred audio language setting
- Playback channel options
- Audio visualizer support
- Fine Tune audio EQ panel

### 💬 Subtitles

- Embedded subtitle track selection
- One-click `CC` subtitle enable/disable button
- External subtitle file loading
- Secondary subtitle support
- Subtitle sync controls
- Subtitle size, color, font, style, and position settings
- Bitmap subtitle handling for PGS/DVD/DVB-style streams
- OpenSubtitles search and download
- Export/burn subtitle workflow support

### 📚 Library

- Drag-and-drop media import
- Add files and folders
- Grid and list layouts
- Favorites
- Continue Watching
- Resume Hub overlay
- Search and sorting
- Multi-select with select all, deselect all, selected count, and delete selected
- Quality labels such as 1080p/4K where detected
- Persistent resume positions and durations

### 🎛️ Pro Tools

- Fine Tune floating panel
- Picture controls
- Audio EQ controls
- Filters
- Bookmarks
- Snapshot tools
- Cast controls
- Mini Player Pro
- Picture in Picture

### 📡 Casting

- AirPlay workflow
- Chromecast discovery/control
- DLNA-style local device discovery
- Roku-style casting service hooks
- Local HTTP server with range request support
- HLS/transcoding helpers for AirPlay scenarios

### ⚙️ Settings

- General playback behavior
- Appearance themes
- Control behavior and mouse gestures
- Keyboard shortcuts
- Video tuning defaults
- Audio defaults and language preferences
- Subtitle defaults and language preferences
- Cast configuration
- Capture/screenshot settings
- TMDB artwork setup
- Watch statistics toggle
- App data/cache reset tools

## 🛠️ Tech Stack

- 🍎 **Swift + SwiftUI** for the macOS app UI
- 🎞️ **FFmpeg** for demuxing, decoding support, thumbnails, and media inspection
- 🧠 **VideoToolbox** for hardware decoding
- 🖥️ **Metal** for rendering and shader-based presentation
- 🔊 **AVFoundation/CoreAudio** for audio output
- 📦 **Sparkle** for updates
- 🛒 **StoreKit 2** for Pro purchase plumbing

## 📁 Project Structure

```text
CBM Media Player/
├── CBM Media Player.xcworkspace       # Open this in Xcode
├── CBM Media Player.xcodeproj
├── CBM Media Player/                  # Main app source
│   ├── AppState.swift                 # Shared app state and playback coordination
│   ├── PlaybackEngine.swift           # Core playback engine
│   ├── VideoPlayerView.swift          # Main player UI
│   ├── MediaLibraryView.swift         # Library, Resume Hub, statistics
│   ├── LibraryThumbnailService.swift  # Library poster/thumbnail generation
│   ├── SeekPreviewGenerator.swift     # Timeline hover previews
│   ├── SubtitleEngine.swift           # Text subtitle parser/timing
│   ├── BitmapSubtitleDecoder.swift    # Bitmap subtitle support
│   ├── AdvancedPanel.swift            # Fine Tune tools
│   ├── SettingsConfiguration.swift    # Settings window
│   ├── TMDBMetadataService.swift      # Optional TMDB artwork integration
│   └── SupportedMediaFormats.swift    # Accepted file extensions
├── CBM Receiver/                      # Companion receiver target
├── Vendor/FFmpeg/                     # Bundled FFmpeg libraries
├── Tools/                             # FFmpeg universal build/verification scripts
└── Pods/                              # CocoaPods workspace support
```

## 🚀 Build & Run

1. Install **Xcode**.
2. Open:

   ```text
   CBM Media Player.xcworkspace
   ```

3. Select the **CBM Media Player** scheme.
4. Choose **My Mac** as the run destination.
5. Build and run with `⌘R`.

### Command Line Build

If `xcodebuild` points to Command Line Tools, use Xcode directly:

```bash
/Applications/Xcode.app/Contents/Developer/usr/bin/xcodebuild \
  -workspace "CBM Media Player.xcworkspace" \
  -scheme "CBM Media Player" \
  -configuration Debug \
  -destination 'platform=macOS' \
  build
```

## 🧪 Verification

Current local verification:

```text
BUILD SUCCEEDED
```

The latest verified build used the installed Xcode app directly because the active developer directory was set to Command Line Tools.

## 🔐 Optional API Setup

### TMDB Artwork

TMDB is optional. When enabled, CBM can use TMDB artwork for library posters. If no TMDB key is configured, CBM falls back to real video-frame thumbnails.

### OpenSubtitles

OpenSubtitles search/download support is available through the subtitle search UI. Embedded and local subtitle files continue to work without online search.

## 🧹 Cache & Data

CBM includes settings to clear app data such as:

- Thumbnail cache
- TMDB artwork cache
- Resume history
- Watch statistics
- Bookmarks
- Playback profiles
- User settings

This is useful when artwork, resume state, tuning, or subtitle preferences need a clean reset.

## 🧰 Developer Notes

- macOS deployment target is currently **14.6** in the Xcode project.
- App bundle identifier: `com.cbmmedia.player`
- Receiver bundle identifier: `com.cbmmedia.player.receiver`
- Use the workspace, not only the project, so package and pod integration resolves correctly.
- FFmpeg universal helper scripts live in `Tools/`.
- Sparkle package is resolved through Swift Package Manager.

## 🗺️ Roadmap Ideas

- More metadata providers
- Smarter episode/season detection
- More subtitle providers
- Playlist export presets
- Deeper HDR calibration tools
- Media info inspector export
- App Store packaging and notarized release pipeline

## 🙌 Credits

Built with SwiftUI, Metal, FFmpeg, VideoToolbox, Sparkle, StoreKit, and a lot of movie-night stubbornness.

