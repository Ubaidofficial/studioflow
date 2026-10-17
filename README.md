# StudioFlow 2026 — In-Browser Screen Studio & Video Editor

> **A professional, 100% client-side screen recorder and video studio in a single HTML file.**  
> Combining ideas from [Dolly](https://dolly-zee.vercel.app/) and [Bolo](https://github.com/NakliTechie/Bolo) with a modern **2026 Nordic Polarnatt** design system — crafted with zero "AI slop", zero build steps, and hardware-accelerated **WebCodecs MP4 export**.

🌐 **Live Web Application**: [https://ubaidofficial.github.io/studioflow/](https://ubaidofficial.github.io/studioflow/)

---

## ⚡ Highlights

- **Zero Install, Zero Build Steps**: Open `index.html` directly in any modern browser (Chrome, Brave, Edge, Arc). No `npm install`, no Docker, no backend server needed.
- **Hardware-Accelerated WebCodecs Export**: Exports native `.mp4` videos at **8×–12× real-time** speed (a 1-minute 1080p 60fps video renders in ~5 seconds).
- **Two Flexible Editing Modes**:
  - **Quick Mode**: Streamlined interface for rapid screen and webcam recordings.
  - **Studio Mode**: Full multi-track timeline, keyframed zooms, device mockups, and privacy controls.
- **Dynamic Voice-Reactive Presenter Bubble**: Presenter webcam bubble automatically pulses and expands with speaking audio volume to hold viewer attention.
- **2026 Polarnatt Design System**: Scandinavian obsidian dark mode, crisp alabaster light mode, 1px hairline borders, and monospace tabular readouts.
- **100% Private**: Your screen recordings and webcam streams never leave your device. Zero telemetry, zero external network requests.

---

## 🎨 Features & Architecture

### 1. Dual Mode Workflow (Inspired by Bolo)
- **Quick Mode**: Collapses all panels and gives full focus to recording and fast exporting. Ideal for quick Loom-style bug reports and asynchronous updates.
- **Studio Mode**: Opens the full inspector and multi-track timeline for professional keynote, product demo, or tutorial videos.

### 2. Studio Canvas & Device Frames
- **macOS Window Frame**: Authentic traffic-light controls (close, minimize, zoom) and customizable window titles.
- **Browser Frame**: Clean modern browser chrome with navigation buttons and address bar.
- **Clean / Borderless**: Modern rounded glass or edge-to-edge presentation.
- **Customizable Padding & Shadows**: Real-time sliders for corner radius, padding, and studio drop shadows.
- **Live Video Blur Wallpaper**: Glassmorphic backdrop that dynamically blurs and diffuses the video behind the frame.

### 3. Voice-Reactive Webcam Presenter Bubble
- **Shapes**: Choose between Circle, Squircle, or Rounded Rect.
- **Smart Corner Snapping**: One-click positioning in Top-Left, Top-Right, Bottom-Left, or Bottom-Right.
- **Audio Pulse Modulation**: Analyzes microphone input via Web Audio API to gently pulse the bubble and glow when speaking.
- **Mirror Mode**: Instant webcam mirroring toggle.

### 4. Smart Pan & Smooth Zoom Keyframing
- **Cubic Bezier Easing**: Smooth, cinematic camera zooms toward points of interest.
- **Interactive Focal Steering**: Click and drag on the canvas to orient the zoom focal point ($X, Y$).
- **One-Click Auto-Detect**: Instantly generates zoom cuts across key segments of the video.
- **Timeline Zoom Blocks**: Draggable and resizable zoom blocks on a dedicated timeline track.

### 5. Privacy & Annotations
- **Drop-in Redaction Blurs**: Blur sensitive passwords, API keys, tokens, or personal identifiers.
- **Shortcut Pill Badges**: Overlay realistic keyboard shortcut badges (e.g., `⌘ + K`, `Ctrl + S`).
- **Voice Clarity Filter**: Built-in audio equalization to enhance vocal presence.

---

## ⏱️ Export Engine: WebCodecs vs. Real-Time Recorders

Most browser-based editors use `MediaRecorder`, forcing you to wait in 1× real-time (a 5-minute video takes 5 minutes to export). 

StudioFlow utilizes the **W3C WebCodecs API** (`VideoEncoder`) paired with **`mp4-muxer`**:

```
[ Canvas Frame Buffer ] ──▶ [ WebCodecs VideoEncoder (H.264) ] ──▶ [ mp4-muxer ] ──▶ [ .mp4 Download ]
                                  (Hardware Accelerated)
```

- **Speed**: 8× to 12× faster than real-time.
- **Quality**: Customizable resolutions (720p, 1080p, 4K) at 30 FPS or 60 FPS.
- **Container**: Native MP4 container compatible with YouTube, X, Slack, and QuickTime.

---

## 🚀 Quick Start

### Option 1: Open Directly from Disk
Simply double-click [`index.html`](file:///Users/usuario/Documents/antigravity/brave-hawking/index.html) or run:
```bash
open index.html
```

### Option 2: Run with a Local Static Server
If you prefer running through `localhost`:
```bash
# Using Python 3
python3 -m http.server 4173

# Or using npx
npx serve .
```
Then visit **`http://localhost:4173`** in your browser.

---

## ⌨️ Keyboard Shortcuts

| Key | Action |
| :--- | :--- |
| `Space` | Play / Pause video preview |
| `S` | Split selected clip at current playhead position |
| `Z` | Add a new Zoom keyframe block at playhead |
| `Delete` / `Backspace` | Remove selected clip, zoom, or redaction block |
| `←` / `→` | Step playhead backward / forward by 0.2s |
| `Shift + ←` / `Shift + →` | Step playhead backward / forward by 2.0s |

---

## 📁 Repository Structure

```text
.
├── index.html               # 100% self-contained application (UI, Canvas engine, audio pipeline)
├── vendor/
│   ├── mp4-muxer.min.js     # WebCodecs MP4 multiplexer library
│   └── webm-muxer.min.js    # WebCodecs WebM multiplexer fallback
└── README.md                # Project documentation
```

---

## 🛡️ Privacy & Security

- **No Telemetry**: There are no tracking scripts, analytics, or external CDNs.
- **100% Offline Capable**: All libraries are bundled locally in the `vendor/` directory.
- **Zero Cloud Uploads**: All audio, video, screen captures, and exports are processed exclusively in your computer's browser memory.

---

## 📄 License

MIT License — Feel free to use, modify, and distribute for personal or commercial projects.
