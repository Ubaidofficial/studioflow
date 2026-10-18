<p align="center">
  <img src="logo.svg" alt="StudioFlow" width="240" />
</p>

# StudioFlow — In-Browser Screen Studio & Video Editor

> **A professional, 100% client-side screen recorder and video studio in a single standalone HTML file.**  
> Faithfully embodying and enhancing the design and workflow of [Dolly](https://dolly-zee.vercel.app/) and [Bolo](https://github.com/NakliTechie/Bolo), fused with 2026 design system patterns from [shadcn/ui](https://github.com/shadcn-ui/ui), [cult-ui](https://github.com/nolly-studio/cult-ui), [animate-ui](https://github.com/imskyleen/animate-ui), [sona-ui](https://github.com/Dinil-Thilakarathne/sona-ui), [velora-ui](https://github.com/ColorlibHQ/velora-ui), and [EasyUI](https://github.com/Surajmaurya1/easyui).  
> **100% Client-Side • Zero Build Steps • Zero Telemetry • Hardware-Accelerated WebCodecs MP4 Export.**

🌐 **Live Web Application**: [https://ubaidofficial.github.io/studioflow/](https://ubaidofficial.github.io/studioflow/)

---

## ⚡ Highlights

- **Zero Install, Zero Build Steps**: Open `index.html` directly in any modern web browser (Chrome, Brave, Edge, Arc, Safari). No `npm install`, no Node.js, no Docker, and no server required.
- **Dolly Design & Workflow**:
  - **Hero Welcome Banner**: Quick "Start recording", "Try the editor", and device status chips (`🎙️ Mic`, `📷 Camera`, `🔊 System audio`, `⚙️`).
  - **3-Step Recording Modal**: Visual selector for *Entire screen*, *A window*, or *A browser tab* + physical camera and microphone device dropdown pickers with live hardware detection.
  - **Top Island Header**: Dolly concentric ring mark, project title renamer, live `• Saved` indicator, Undo/Redo buttons, light/dark theme switch, and solid Royal Blue `#2563EB` Export button.
- **Interactive Multi-Track Timeline (Dolly Screenshot 3)**:
  - **Filmstrip Thumbnails**: Visual frame strip depicting clip contents across the timeline.
  - **Audio Waveform Overlay**: Real-time organic speech waveform bars rendered directly over the video clip.
  - **In-Track Zoom Badge Pills**: Numbered zoom factor pills (e.g. `1  1.55x`) floating directly inside the video lane with drag handles to reposition keyframes.
  - **Subtitles & Captions Lane**: Draggable subtitle cue blocks with instant timing adjustment and canvas overlay pills.
- **Presenter Camera Bubble**:
  - **4 Dolly Shapes**: Circle (`○`), Squircle (`▢`), Capsule (`⬯`), and Rounded Rectangle (`▭`).
  - **4 Smart Corner Snaps**: Top-Left (`⌜`), Top-Right (`⌝`), Bottom-Left (`⌞`), Bottom-Right (`⌟`).
  - **Free Canvas Dragging**: Click and drag the presenter bubble anywhere on the preview canvas with real-time cursor feedback and corner snapping.
  - **5 Border Styles**: None, White, Black, Royal Blue, and Purple.
  - **Sliders**: Smooth controls for Size (15%–120%), Zoom (1.0×–2.5×), and Drop Shadow (0%–100%).
- **Local AI Browser Captions**:
  - Transcribes speech locally inside browser memory — nothing leaves your machine.
  - Multi-language support: English, Urdu (`اردو`), Spanish, French, German, Hindi, Chinese, Japanese, Arabic.
  - One-click *Generate again*, inline subtitle editing, and keyboard shortcut (`T`) to insert subtitles at playhead.
- **Studio Audio Suite**:
  - Master volume slider (0%–200%).
  - One-click *Enhance voice* vocal presence filter.
  - *Trim silence* tool to remove dead air automatically.
- **Complete Undo / Redo History**: Full state snapshots supporting `⌘Z` (Undo) and `⌘⇧Z` (Redo) across all edits, moves, cuts, and inspector settings.
- **Hardware-Accelerated WebCodecs Export**: Exports native `.mp4` video files at **8×–12× real-time** speed via `VideoEncoder` and `mp4-muxer`.

---

## 🎨 Design System & Visual Architecture

### 1. Dolly Welcome Hero & 3-Step Setup
The studio greets you with Dolly's welcome card:
- **Hero Actions**: Start recording with 1 click or explore demo content with "Try the editor".
- **Step 1 of 3 Modal**: Visual cards for screen type (*Entire screen*, *A window*, *A browser tab*), hardware camera/microphone selection via `navigator.mediaDevices.enumerateDevices()`, and system audio capture switch.

### 2. Multi-Track NLE Timeline
A desktop-grade timeline inspired by Dolly and modern video editors:
- **Ruler Track**: Sub-second and second interval markings.
- **Clip Track**: Seamless clip block with filmstrip frame thumbnails, audio waveform overlay, and draggable floating zoom factor badges.
- **Captions Track**: Clear subtitle blocks that sync with canvas overlay rendering.
- **Playhead**: Scrubbable playhead needle with smooth frame-by-frame seeking.

### 3. Studio Stage & Device Frames
- **macOS Window Frame**: Authentic traffic-light controls (close, minimize, zoom) with custom titles.
- **Browser Frame**: Clean modern browser chrome with navigation buttons and URL bar.
- **Clean / Borderless**: Modern rounded glass presentation.
- **Customizable Aspect Ratios**: Floating island for Original, 16:9, 9:16 (Shorts/Reels/TikTok), 1:1 (Square), and 4:5.
- **Background Gradients**: Dolly Sunset, Coral, Sky, Lavender, Pearl, Midnight, Ocean, and Cyber presets, plus Live Video Blur Wallpaper.

### 4. EasyUI Animated Motion Suite ([Surajmaurya1/easyui](https://github.com/Surajmaurya1/easyui))
- **Dynamic Island Status Pill (`DynamicIsland.tsx`)**: Header capsule morphing between idle ready state, recording timecounter, and export progress.
- **Global ⌘K Command Palette (`CommandMenu.tsx`)**: Full keyboard-driven command menu for lightning-fast action execution.
- **Cursor Spotlight Following Cards (`SpotlightCard.tsx`)**: Radial hairline border illumination tracking mouse movement.
- **Magnetic Proximity Action Buttons (`MagneticButton.tsx`)**: Physical spring attraction pulling key buttons toward the cursor on hover.

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
- **Container**: Native MP4 container compatible with YouTube, X, Slack, Discord, and QuickTime.

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
| `⌘Z` / `Ctrl + Z` | Undo last action |
| `⌘⇧Z` / `Ctrl + Shift + Z` | Redo last action |
| `⌘K` / `Ctrl + K` | Open Command Menu Palette |
| `Space` | Play / Pause video preview |
| `S` | Split clip at playhead position |
| `Z` | Add Zoom keyframe at playhead |
| `T` | Add Subtitle / Caption at playhead |
| `Delete` / `Backspace` | Remove selected clip, zoom, caption, or blur |
| `←` / `→` | Step playhead backward / forward by 0.2s |
| `Shift + ←` / `Shift + →` | Step playhead backward / forward by 2.0s |
| `Esc` | Dismiss modals or Command Menu |

---

## 💎 Brand Identity & Vector Assets

StudioFlow features a minimal, modern 2026 brand identity built around the **Dual-Track Monogram**:
- **Design Philosophy**: Fuses the essence of a recording studio (aperture, lens, focal center) with continuous workflow (two counter-balanced timeline tracks forming an iconic "S" monogram).
- **Optical Precision**: Perfectly balanced cubic Bézier curvature with round caps, delivering immediate legibility from a 16px favicon up to high-DPI retina displays.
- **Adaptive Typography**: Features responsive SVG typography that harmonizes with both dark and light modes automatically.

---

## 📁 Repository Structure

```text
.
├── index.html               # 100% self-contained application (UI, Canvas engine, WebCodecs pipeline)
├── logo.svg                 # Full vector horizontal lockup (Dual-Track mark + adaptive typography)
├── logo-mark.svg            # Standalone high-res squircle app mark with deep midnight gradients
├── logo-symbol.svg          # Pure vector glyph without background for flexible integration
├── favicon.svg              # Pixel-perfect 32x32 SVG favicon for browser tabs
├── logo-showcase.html       # Brand identity exploration lab & design system comparison
├── vendor/
│   ├── mp4-muxer.min.js     # WebCodecs MP4 multiplexer library
│   └── webm-muxer.min.js    # WebCodecs WebM multiplexer fallback
└── README.md                # Project documentation
```

---

## 🛡️ Privacy & Security

- **No Telemetry**: Zero tracking scripts, cookies, or external analytics.
- **100% Offline Capable**: All libraries are bundled locally in the `vendor/` directory.
- **Zero Cloud Uploads**: All audio, video, screen captures, speech transcriptions, and exports are processed exclusively in your computer's browser memory.

---

## 📄 License

MIT License — Feel free to use, modify, and distribute for personal or commercial projects.
