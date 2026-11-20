# 🛡️ OVERWATCH — Tactical Vision Intelligence Lab

> **"Ever wanted to be the tech genius behind a superhero or spy movie? The one who zooms into surveillance footage, tracks a suspicious vehicle, analyzes tiny details, and uncovers something everyone else missed?"**

Welcome to **OVERWATCH**, a mission-control intelligence application built for the **OVERWATCH Challenge by Harshad & ImageKit**. OVERWATCH transforms ordinary images and surveillance videos into a cinematic, interactive tactical intelligence experience using **ImageKit's real-time media transformations**, **MCP servers**, and **edge computer vision**.

---

## 🏆 Presentation Decks for Judges & Hackathon Evaluators

* 🌟 **Simple Presentation & Judge Pitch Guide (Plain English):** [SIMPLE_JUDGES_PITCH.md](./SIMPLE_JUDGES_PITCH.md)
* 📑 **Official Judging Presentation Deck (Technical / Full Matrix):** [OVERWATCH_JUDGES_PRESENTATION_DECK.md](./OVERWATCH_JUDGES_PRESENTATION_DECK.md)
* 🖥️ **Interactive Cyberpunk HTML Pitch Deck:** [OVERWATCH_PITCH_DECK.html](./OVERWATCH_PITCH_DECK.html) *(Open in browser with keyboard controls `[←] [→]`, `[S]` for Speaker Notes, and `[F]` for Fullscreen)*
* 📖 **Operator Field Guidebook:** [OVERWATCH_FIELD_GUIDE_AND_PPT.md](./OVERWATCH_FIELD_GUIDE_AND_PPT.md)

### 🎯 Hackathon Rubric Scorecard
| Judging Criterion | Weight | OVERWATCH Implementation Highlight |
| :--- | :---: | :--- |
| **ImageKit Platform Depth & Elegance** | **25%** | Sub-pixel `cm-extract:w-880`, `fo-car`/`fo-face` smart crops, layered edge HUD compositor (`l-image`/`l-text`), and remote MCP server workflows. |
| **Engineering Rigor & CV Accuracy** | **25%** | YCrCb skin chrominance mask eliminates wheel rims falsely flagged as faces; HSV yellow/white plate filters reject asphalt parking lines & roof slats; CLAHE + Otsu binarization. |
| **Real-World Utility & Problem Significance** | **20%** | Solves sparse camera environments via Chokepoint Intercept Theory and Temporal Breadcrumb linking. |
| **Investigation Workflow & Forensic Integrity** | **15%** | Persistent Most Wanted Gangster Registry, "Places where they made a mess" crime logs, SHA-256 evidence sealing, and zero-hallucination clean record protection. |
| **UI/UX & Live Demo Polish** | **15%** | High-tech cyberpunk tactical HUD across 8 mission tabs; 1-click bundled master video for immediate testing. |


---

## ⚡ Mission Features at a Glance

| Feature | Description | ImageKit & CV Technology |
| :--- | :--- | :--- |
| **🛰️ Video Surveillance & Tracking** | Ingest MP4/MOV footage or procedural CCTV feeds. Real-time multi-target tracking across timeline. | OpenCV Multi-Cascade (Face, Person, Vehicle) + Sharpness Metric |
| **🚨 Most Wanted & Criminal Registry** | Cross-reference car number plates and faces against a persistent gangster database. Tracks past crime scenes ("where they made a mess") and logs new accusations. | Persistent JSON Registry (`criminal_registry.json`) + Biometric Cross-Correlation |
| **🚘 License Plate Intelligence (ALPR)** | Detect and verify car number plates against flagged syndicate vehicles (e.g. `7X9`, `7X9-B42`, `APX-901`). | High-Speed Plate Query & Flagged Alert Network |
| **⚖️ Temporal Frame Comparison** | Pinpoint minute movements, tampering, or intruders across surveillance intervals. | Absolute Pixel Delta + False-Color Thermal Difference Heatmap (`COLORMAP_JET`) |
| **📐 Forensic Detail Zoom** | Extract exact pixel bounds (license plates, badges, hidden objects) with center/top-left targeting. | ImageKit `cm-extract` + Chained Super-Resolution (`:w-880`) |
| **📏 Distance & Scale Calibration** | Laser-measure distances between suspects, vehicles, and perimeter points in pixels and meters. | Calibrated Ground Euclidean Vector Geometry |
| **🎯 Smart Focus & Object Recon** | Intelligently crop faces and COCO objects without manual coordinates. Zoom in/out dynamically. | ImageKit `fo-face,z-2.0`, `fo-car,z-1.4`, `fo-truck_car_train`, `ar-16_9` |
| **🧠 Visual Intel & Scene Profiling** | Autonomous scene analysis, person headcount, text/plate extraction, and threat verification. | ImageKit `ai-tasks` (`select_tags`, `yes_no`) + `ai-auto-description` |
| **🎨 Layered Evidence Board** | Assemble multi-layer tactical HUD overlays, threat alert bounding boxes, and suspect tags. | ImageKit Layer Engine (`l-image,i-ik_canvas`, `l-text`, 00-99 opacity) |
| **🤖 MCP Transformation Builder** | Natural language to ImageKit URL compiler + ready-to-copy client configs. | ImageKit DevTools MCP Server (`devtools-mcp.imagekit.io/mcp`) |
| **📋 Cryptographic Dossier** | Full forensic report with source byte SHA-256 seal and structured JSON evidence manifest. | Tamper-Evident SHA-256 Hash + JSON Export |

---

## 🚀 Quick Start

### 1. Installation

```bash
git clone <repo-url>
cd overwatch_demo

# Set up virtual environment
python -m venv .venv

# Activate environment
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 2. Run Mission Control

```bash
streamlit run app.py
```

Open `http://localhost:8501` in your browser.

---

## 🎮 1-Click Instant Demo Scenarios (No Files Needed!)

Don't have surveillance video on hand? OVERWATCH includes a **built-in procedural surveillance simulation engine**:

1. In the sidebar, select a mission scenario:
   - **Scenario Alpha: Perimeter Vehicle Intercept** (night-time moving vehicle with license plate + pedestrian)
   - **Scenario Bravo: High-Security Terminal Face Track**
   - **Scenario Charlie: Movement & Anomaly Detection**
2. Click **🚀 Load Scenario Simulation**.
3. OVERWATCH automatically synthesizes a high-contrast CCTV feed with tactical telemetry, analyzes it across time, registers targets, and calculates edge sharpness.

---

## 🛠️ ImageKit URL Transformation Architecture

Every transformation in OVERWATCH leverages ImageKit's real-time edge URL parameters:

### 1. Smart Object & Face Focus (`fo-<object>`, `fo-face`)
```text
https://ik.imagekit.io/ikmedia/docs_images/features/image-transformations/car.jpeg?tr=fo-car,z-1.4,ar-2_1
https://ik.imagekit.io/ikmedia/docs_images/examples/example_portrait_1.jpg?tr=w-150,h-150,fo-face,z-2.0
```

### 2. High-Precision Coordinate Extraction (`cm-extract`)
```text
https://ik.imagekit.io/ikmedia/docs_images/examples/example_food_3.jpg?tr=w-300,h-300,cm-extract,x-100,y-300:w-880
```
- Extracts a 300x300 region at `(100, 300)` without initial distortion.
- Chains `:w-880` to blow up the evidence for forensic examination.

### 3. Layered Evidence Overlays (`l-image`, `l-text`)
```text
https://ik.imagekit.io/ikmedia/docs_images/features/image-transformations/car.jpeg?tr=l-image,i-ik_canvas,w-380,h-240,bg-transparent,b-6_00FFCC,lx-80,ly-90,l-end:l-text,i-TARGET%20IDENTIFIED,fs-32,co-00FFCC,bg-0A1424,pa-8,lx-80,ly-40,l-end
```
- Draws a glowing tactical bounding box outline and callout badge directly on the CDN edge.

---

## 🤖 ImageKit Model Context Protocol (MCP) Integration

OVERWATCH is architected to work hand-in-hand with ImageKit's remote MCP servers:

| MCP Server | Endpoint | Purpose |
| :--- | :--- | :--- |
| **DevTools** | `https://devtools-mcp.imagekit.io/mcp` | Natural language transformation builder & documentation lookup (No auth needed) |
| **DAM** | `https://imagekit.io/mcp/dam` | Natural language asset search, tagging, and library management |
| **Admin** | `https://imagekit.io/mcp/admin` | Storage origins, endpoint settings, and usage analytics |

### Ready Configuration for AI Coding Clients:

#### Claude Desktop & Cursor (`claude_desktop_config.json`):
```json
{
  "mcpServers": {
    "imagekit_devtools": {
      "command": "npx",
      "args": ["-y", "@imagekit/mcp-server", "--url", "https://devtools-mcp.imagekit.io/mcp"]
    },
    "imagekit_dam": {
      "command": "npx",
      "args": ["-y", "@imagekit/mcp-server", "--url", "https://imagekit.io/mcp/dam"]
    }
  }
}
```

---

## 🔒 Forensic Integrity & Chain of Custody

All processed media in OVERWATCH is cryptographically sealed with a **SHA-256 checksum** calculated immediately upon acquisition. The full detection timeline, coordinate bounds, sharpness scores, and transformation manifests can be downloaded with a single click as `overwatch_forensic_dossier.json`.

---

*Developed for the OVERWATCH Challenge. Built with Streamlit, OpenCV, ImageKit Media APIs, and Python.*
