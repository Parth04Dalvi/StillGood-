# StillGood? 🥗🏷️

> **A food freshness sentinel, leftover tracker, and physical container labeling system aligned with USDA FSIS & FDA guidelines.**

[![License: MIT](https://img.shields.io/badge/License-MIT-emerald.svg)](LICENSE)
[![Zero-Dependency](https://img.shields.io/badge/Runtime-Vanilla%20JS%20%2F%20Tailwind-blue.svg)](#built-with)
[![Offline-First](https://img.shields.io/badge/Storage-Local%20First-purple.svg)](#architecture)

---

## 📌 Problem & Motivation

- **Misleading Food Labels:** Over 80% of consumers prematurely discard safe food due to confusing *"Best By"*, *"Sell By"*, and *"Use By"* stamps, which generally reflect manufacturer quality estimates rather than actual safety thresholds.
- **The "Clock Reset" Trap:** Once factory packaging is broken, or once a meal is cooked and stored, the printed expiration date becomes completely irrelevant. Pathogens like *Bacillus cereus* (in rice/pasta) and *Listeria monocytogenes* (in deli items) multiply regardless of the original printed date.
- **The Container Blind Spot:** Leftovers stored in Tupperware, Mason jars, or deli containers quickly turn into anonymous "fridge science experiments" because nobody remembers the exact prep date.

**StillGood?** solves this through a zero-latency web application paired with a physical smart-label generation system.

---

## ✨ Key Features

### 1. Real-Time Freshness Diagnostic
- Select from a curated codex of perishable categories (poultry, dairy, seafood, cooked starches, produce).
- Dynamic calculations adjust safe shelf-life based on:
  - **Item Condition:** Raw/Uncooked, Cooked Leftover, or Once Opened.
  - **Storage Environment:** Refrigerator ($\le 40^\circ\text{F}$), Deep Freeze ($0^\circ\text{F}$), or Room Temperature.
  - **Elapsed Time:** Relative chips (*Today*, *Yesterday*, *3–5 days*) or explicit date stamps.
- Color-coded safety verdicts: **Safe to Eat**, **Eat Today / Freeze**, or **High Risk / Discard**.

### 2. Cooked Food & Takeout Triage
- Dedicated evaluation for high-risk prepared foods and takeout.
- Enforces the critical **2-Hour Rule** (reduced to **1 Hour** in conditions $>90^\circ\text{F}$ / $32^\circ\text{C}$).
- Accounts for pathogen persistence (e.g., heat-stable enterotoxins produced by *Staphylococcus aureus* and *Bacillus cereus*).

### 3. "My Fridge" Inventory & Kitchen Tools
- **Live Leftover Tracker:** Tracks remaining safe days with automated badges (`Eat today!`, `Expired X days ago`).
- **Priority Action Queue:** Instantly flags the top items needing consumption or freezing.
- **Appliance Temperature Log:** Tracks refrigerator temperature logs to maintain the target $\le 40^\circ\text{F}$ threshold.
- **Integrated Shopping List:** Quick one-click "Restock" feature from tracked food items directly to an active shopping list.
- **Barcode Lookup:** Integrates with Open Food Facts API to retrieve product details via 8–14 digit UPC/EAN barcodes.
- **Privacy-Preserving Recipe Prompts:** Client-side photo preview and pantry-match suggestions without sending media to external cloud servers.

### 4. Printable Container Sticker System
- Generates high-contrast, physical labels formatted for Mason jars, Pyrex dishes, and deli containers.
- Formats dates into an unmistakable **"DO NOT EAT AFTER"** block.
- Supports **Modern Pill** and **Retro Deli Tag** styles.
- Integrated print stylesheet (`@media print`) pre-configured for sheet-printing or direct thermal-roll printing.

### 5. USDA Codex & Label Decoder
- Searchable reference table detailing unopened, opened, cooked, and freezer shelf-life intervals.
- Specific pathogen alerts (*Salmonella*, *Listeria*, *Campylobacter*, *Histamine*).
- Educational guide breaking down federal labeling regulations and debunking critical food safety myths.

---

## 🛠️ Built With

- **Markup & Layout:** HTML5, Semantic Elements
- **Styling:** [Tailwind CSS](https://tailwindcss.com/) (via CDN) with full Dark/Light theme switching
- **Icons:** [Lucide Icons](https://lucide.dev/)
- **Micro-Interactions:** [Canvas Confetti](https://github.com/catdad/canvas-confetti)
- **External API:** [Open Food Facts REST API v2](https://world.openfoodfacts.org/) (Barcode resolution)
- **State & Storage:** Native browser `localStorage` and `Blob` JSON export/import

---

## 🚀 Getting Started

No build step, Node environment, or bundler is required.

### Quick Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/stillgood.git](https://github.com/your-username/stillgood.git)
   cd stillgood
