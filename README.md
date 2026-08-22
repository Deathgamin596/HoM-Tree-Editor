# Heart of Magic Tree Editor

A desktop tool for visualizing and editing spell trees for the Heart of Magic mod. It reads scanned spell records, organizes them into radial school-based trees, and lets you refine prerequisites, themes, and layout before exporting a JSON file you can copy and paste the contents of into the import feature of HoM.

## What It Does

1. **Import / Scan** — Load a JSON scan of spells from the Heart of Magic mod or import an existing JSON file.
2. **Tree Building** — Automatically groups spells by school, assigns tiers based on skill level, and lays them out in radial sectors.
3. **Visual Editing** — Pan, zoom, drag, multi-select, and link nodes with hard/soft prerequisites in an interactive canvas.
4. **Refine** — Edit display names, themes, lock positions, and rerun the tree builder with different rules without losing manual work.
5. **Export** — Save the finalized grimoire as JSON for use with the Heart of Magic mod.

## Key Features

- **Radial Tree Layout** — Each school gets its own sector; tiers are arranged from Novice (core) out to Master.
- **Smart Linking** — Automatic parent assignment respects tier gaps, theme matching, and a 3-child cap.
- **Search** — Quickly find spells by name or Form ID from the dashboard or header.
- **Node Editor** — Inspect and adjust individual spell metadata, coordinates, and connections.
- **Dashboard** — Overview of schools, node counts, and skill distribution.
- **Undo / History** — Step back through edits.
- **Standalone Desktop App** — Built with Tauri for a native Windows, macOS, or Linux experience.

## Building the Standalone Application (Tauri)

The editor can be compiled as a native desktop application for Windows, macOS, or Linux using [Tauri](https://tauri.app/).

### Prerequisites

1.  **Rust**: [Install the Rust toolchain](https://www.rust-lang.org/tools/install).
2.  **Node.js**: [Install Node.js (LTS recommended)](https://nodejs.org/).
3.  **OS Dependencies**:
    *   **Windows**: [WebView2](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) and C++ Build Tools.
    *   **macOS**: Xcode Command Line Tools.
    *   **Linux (Ubuntu/Debian)**: 
        ```bash
        sudo apt-get install -y libgtk-3-dev libwebkit2gtk-4.0-dev libappindicator3-dev librsvg2-dev patchelf
        ```

### Build Steps

1.  **Install Dependencies**:
    Open your terminal in the project root and run:
    ```bash
    npm install
    ```

2.  **Build the Standalone App**:
    Generate the production-ready executable:
    ```bash
    npm run tauri build
    ```
    *The standalone program will be found in `src-tauri/target/release/bundle/`.*

### Local Development
To run the editor with hot-reloading in a desktop window:
```bash
npm run tauri dev
```
