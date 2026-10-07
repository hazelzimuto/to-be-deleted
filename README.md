# RouteNote — Revenue Sharing Hub & Design System

A high-fidelity prototype and UI/UX design suite for the **RouteNote Revenue Sharing Hub**, featuring arrangement management, multi-participant royalty splits, track-level override configuration, and custom 20×20px vector icon assets.

---

## 📌 Project Overview

The Revenue Sharing Hub enables RouteNote artists, record labels, and collaborators to seamlessly manage royalty distributions across releases and tracks. This repository contains the interactive functional workspace prototype alongside vector design assets tailored to RouteNote's dark-mode design system.

### Core Objectives
* **Role-Based Visibility**: Distinct views and actions for **Release Owners** (full configuration, participant invites, split editing) vs. **Recipients** (read-only payout tracking, status monitoring).
* **Mixed Revenue Sharing**: Support for release-level base splits with granular per-track overrides for complex collaborations.
* **Custom Iconography System**: Purpose-built 20×20px icons adhering strictly to a 2px stroke weight and sharp geometric vertices (zero rounded edges).

---

## 🚀 Key Features

### 1. Interactive Workspace (`index.html`)
* **Dynamic Role Switcher**: Instant toggle between *Release Owner* and *Recipient* modes with automatic UI adaptation and metric card re-calculation.
* **Metrics Dashboard**: Real-time summary cards displaying:
  * Total arrangements and active tracks
  * Ownership vs. participation ratios
  * SmartHub pending requests
  * Scope breakdown (Release, Track, Mixed, Multi-track)
* **Arrangement Controls & Filtering**: Full search bar (title, UPC, ISRC, participant) and multi-level filters (Scope and Role).
* **High-Density Table View**: Clean, compact arrangement table with clear status badges, participant pills, and direct edit triggers.
* **Mixed Arrangement Editor**: Dedicated panel for managing uniform base shares and per-track participant overrides (supporting up to 5-user splits).
* **Modal Workflows**: Built-in modals for *New Revenue Share Request* and *Complete Revenue Sharing Report Export*.

### 2. Tab Icon System (Owned vs. Shared)
Designed specifically for the workspace's primary view tabs:

| Tab | Role | Approved / Proposed Icon | Design Specifications |
| :--- | :--- | :--- | :--- |
| **Owned By You** | Master Release Owner | **Sharp Music Folder** | 20×20px grid, 2px stroke, 100% sharp 90°/45° vertices, geometric music note glyph (`rect` notehead + 90° flag). |
| **Shared With You** | Recipient / Participant | **Sharp Inward Arrow Folder** *(or approved branching tree)* | 20×20px grid, 2px stroke, identical sharp folder base, downward angular entry arrow. |

---

## 📂 Repository Structure

```text
├── index.html                       # Primary RouteNote Revenue Sharing Hub interactive prototype
├── sharp_folder_icons.svg           # Figma-ready vector pair: Sharp Music Folder & Inward Arrow Folder (No rounded edges)
├── sharp_folder_mockups.html        # Interactive comparison tool for sharp-edge folder variations
├── folder_icons_pair.svg            # Standalone vector assets for folder-based concept explorations
├── folder_icon_mockups.html         # Interactive comparison tool for folder design concepts
├── option_5_origin_source_node.svg  # Standalone vector for Option 5 (Origin Source Node)
├── origin_source_node_variants.svg  # Figma artboard with 3 subtle variants of the Origin Source Node
├── icon_mockups.html                # Visual comparison of the initial 6 icon design options
├── .vscode/
│   └── settings.json                # Live Server configuration (default port: 5502)
└── README.md                        # Project documentation and asset guide
```

---

## 🎨 Icon Vector Specifications

All SVG assets in this project conform to strict geometric criteria:
* **ViewBox**: `0 0 20 20`
* **Stroke Width**: `2px`
* **Edge Style**: **Zero rounded edges** (`rx="0"`, sharp 90° and 45° miter vertices)
* **Color Handling**: `stroke="currentColor"` for dynamic theme inheritance (white on active blue fill, blue on periwinkle background).

### SVG Snippets

#### Owned By You — Sharp Music Folder (`20×20px`)
```xml
<svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="2">
  <!-- Sharp Folder Perimeter (No Rounded Corners) -->
  <path d="M2 5h5l2 2h9v9H2V5z"/>
  <!-- Sharp Geometric Music Note -->
  <rect x="7" y="11" width="3" height="3" fill="currentColor" stroke="none"/>
  <path d="M10 11V8h3v2"/>
</svg>
```

#### Shared With You — Sharp Inward Arrow Folder (`20×20px`)
```xml
<svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="2">
  <!-- Matching Sharp Folder Perimeter -->
  <path d="M2 5h5l2 2h9v9H2V5z"/>
  <!-- Sharp Angular Inward Arrow -->
  <path d="M10 8v5M7.5 10.5L10 13l2.5-2.5"/>
</svg>
```

---

## 💻 How to View & Run Locally

### Option 1: Direct Browser Launch (macOS)
Double-click any `.html` file in Finder, or execute from your terminal:
```bash
# Open primary Revenue Sharing Hub prototype
open index.html

# Open sharp folder icon comparison showcase
open sharp_folder_mockups.html

# Open all-options icon showcase
open icon_mockups.html
```

### Option 2: VS Code Live Server
1. Open the project folder in **Visual Studio Code**.
2. Click **Go Live** in the bottom status bar (configured to port `5502` via `.vscode/settings.json`).
3. Navigate to `http://127.0.0.1:5502/index.html`.

### Option 3: Importing Vectors into Figma
1. Drag and drop `sharp_folder_icons.svg` or `origin_source_node_variants.svg` directly onto your Figma canvas.
2. Alternatively, copy any of the SVG XML blocks above and press <kbd>Cmd</kbd> + <kbd>V</kbd> in Figma to paste as native, editable vector nodes.

---

## 🛠 Design Tokens Reference

| Token | Value | Purpose |
| :--- | :--- | :--- |
| `--rn-blue` | `#1346ba` | Primary brand accent & active tab background |
| `--rn-blue-inactive` | `#dce4f7` | Secondary/inactive tab background |
| `--rn-teal` | `#00d2b3` | Status highlights, success indicators |
| `--bg-main` | `#0b0f19` | Main hub background (dark mode) |
| `--bg-card` | `#131b2e` | Card & table elevated surface |
| `--border-color` | `#233152` | Primary container borders |
| `--text-main` | `#f1f5f9` | High-contrast body & heading typography |
| `--text-muted` | `#94a3b8` | Subtitles, labels, and metadata |

---

## 📄 License
Internal prototype and design exploration for RouteNote. All rights reserved.
