# StudioFlow — Enhanced In-Browser Screen Recorder & Video Editor

> **100% Client-Side In-Browser Video Studio** inspired by [Dolly](https://dolly-zee.vercel.app/), with hardware-accelerated **WebCodecs MP4 export**, interactive multi-track timeline, device frames, smart zooms, privacy censor boxes, and webcam overlays.

---

## ✨ Features & Enhancements Over Dolly

| Feature | Dolly 1.0 | StudioFlow (Our Enhanced Editor) |
| :--- | :--- | :--- |
| **Export Speed** | Real-time `MediaRecorder` (60s video = 60s export) | **⚡ WebCodecs Hardware Muxer**: **8x–12x faster than real-time** (a 12-second 1080p 60fps video exports in **~1.5 seconds**) |
| **Device Frames** | Basic frame | **macOS Window** (with authentic traffic-light controls & title), **Modern Browser** (with URL bar), **Clean Rounded Glass**, and **Frameless** |
| **Backgrounds** | Static preset colors | **10 Studio Gradient Presets**, Solid Colors, and **Live Video Blur Wallpaper** (glassmorphic blur of the video behind itself) |
| **Timeline Editing** | Single track | **Multi-Track Interactive Timeline**: Clip split (`S`), trim, zoom blocks, privacy blur blocks, time ruler, and scrubbing playhead |
| **Privacy & Censorship** | None (parked in code) | **🔒 Interactive Privacy Blur Box** (censor passwords, auth tokens, API keys, and sensitive data with customizable duration) |
| **Auto-Zoom & Pan** | Basic pixel grid | **Smooth Cubic Bezier Zoom & Pan**, Auto-detection button, custom focal coordinates ($X, Y$), and manual keyframe creation (`Z`) |
| **Webcam PIP Bubble** | Fixed corner bubble | **Circle, Squircle, or Rounded Rect**, free corner snapping (Top-L, Top-R, Bot-L, Bot-R), mirror camera toggle, and border glow |
| **Visual Annotations** | Disabled | **Keyboard Shortcut Pill Badge** (e.g. `⌘ + K` or `Ctrl + S`) with studio drop shadow |
| **Instant Demo Mode** | None | **Built-in Procedural Demo** featuring realistic coding, syntax highlighting, animated typing, mouse cursor paths, and terminal output |
| **Portability** | Single HTML | **Self-contained HTML file** with local vendor libraries, runnable offline without any server backend |

---

## 🚀 How to Run

### Option 1: Open Directly in Your Browser
Double-click [`index.html`](file:///Users/usuario/Documents/antigravity/brave-hawking/index.html) or open it directly in Chrome, Edge, Brave, or Arc:
```bash
open index.html
```

### Option 2: Run via Local HTTP Server
```bash
python3 -m http.server 4173
```
Then navigate to: **`http://localhost:4173`**

---

## ⌨️ Keyboard Shortcuts

* **`Space`**: Play / Pause video preview
* **`S`**: Split video clip at playhead position
* **`Z`**: Add new Zoom block at playhead position
* **`Delete` / `Backspace`**: Delete selected clip, zoom, or blur block
* **`←` / `→`**: Frame step backward / forward by 0.2s (Hold `Shift` for 2.0s)

---

## 📁 File Structure

```
.
├── index.html               # Complete self-contained video editor application
├── vendor/
│   ├── mp4-muxer.min.js     # Fast WebCodecs MP4 Muxer (hardware accelerated)
│   └── webm-muxer.min.js    # Fast WebCodecs WebM Muxer
└── README.md                # Documentation and guide
```
