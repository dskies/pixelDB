# 🎮 Pixel Art Adventures DB

> A curated, searchable database of pixel-art adventure and indie games — from 1984 classics to 2026 upcoming releases.

**Live demo:** [https://dskies.github.io/pixelDB](https://dskies.github.io/pixelDB)  
**Repository:** [https://github.com/dskies/pixelDB](https://github.com/dskies/pixelDB)

---

## Overview

**Pixel Art Adventures DB** is a single-page, zero-dependency web application that lets you browse, filter, search, and sort a hand-curated collection of **299 pixel-art games** — spanning Point-and-Click adventures, action platformers, metroidvanias, RPGs, puzzles, and narrative experiences.

The dataset covers releases from **1984** (the dawn of the genre with King's Quest) through **2026** (upcoming titles), with bilingual support in **Italian 🇮🇹** and **English 🇬🇧**.

---

## Features

| Feature | Description |
|---|---|
| **Bilingual** | Full Italian / English toggle (separate CSV datasets) |
| **Filter buttons** | Quick-filter by tag: Must Play ★, Cyberpunk, Noir, Mystery, Sci-Fi, Cozy, Horror, RPG, Classic |
| **Live search** | Real-time filtering by title, notes, tags, genre, or year |
| **Sortable columns** | Sort by index, year, or title (ascending / descending) |
| **Clickable tags** | Click any tag badge in the table to instantly filter by it |
| **Ambient audio** | Optional background music with autoplay + manual fallback |
| **Retro UI** | CRT scanline effect, neon-green terminal aesthetic, pixel fonts |
| **Zero dependencies** | Pure HTML + CSS + JavaScript — no frameworks, no build tools |
| **Static hosting** | Runs on GitHub Pages, Netlify, Vercel, or any HTTP server |

---

## Project Structure

```
pixelDB/
├── index.html       # Application shell: layout, styles, logic (single file)
├── games.csv        # Dataset in Italian (299 entries)
├── games_eng.csv    # Dataset in English (299 entries)
├── z.mp3            # Ambient background audio
├── LICENSE          # MIT License
└── README.md        # This file
```

---

## Dataset Format

Both CSV files share the same schema:

| Column | Type | Description |
|--------|------|-------------|
| `num` | integer | Sequential index |
| `year` | integer | Release year (or expected year for upcoming titles) |
| `title` | string | Official game title |
| `genre` | string | Primary genre (`Action`, `Puzzle`, `P&C`, `RPG`, `Sim`, `Adventure`, `Narrative`) |
| `tags` | string | Comma-separated tags (e.g. `"cyberpunk,noir"`) |
| `star` | boolean | `true` = Must-Play recommendation |
| `note` | string | Short editorial description |

### Available Tags

`cyberpunk` · `noir` · `mystery` · `scifi` · `cozy` · `horror` · `rpg` · `classic`

---

## How to Run

### Option A — Local (requires HTTP server)

The app fetches CSV files via `fetch()`, so it cannot run directly from `file://`. Use any local server:

```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .

# VS Code
# Install the "Live Server" extension, then click "Go Live"
```

Then open [http://localhost:8080](http://localhost:8080) in your browser.

### Option B — GitHub Pages (recommended)

1. Push the repository to GitHub.
2. Go to **Settings → Pages → Source → Deploy from a branch → `main` / `(root)`**.
3. The app will be live at `https://<username>.github.io/<repo>/`.

---

## Contributing

Contributions are welcome. To propose a new entry or correction:

1. Fork the repository.
2. Edit `games.csv` and `games_eng.csv` (keep both in sync).
3. Submit a Pull Request with a brief description of the change.

> **Please do not alter the column order or encoding (UTF-8 without BOM).** Both files must remain consistent.

---

## Legal Notices & Attributions

### 1. Source Code License

Copyright (c) 2024–2026 dskies

The source code in this repository (`index.html`) is released under the **MIT License**.  
See the [LICENSE](LICENSE) file for the full text.

---

### 2. Fonts (Google Fonts)

This project uses two typefaces served via [Google Fonts](https://fonts.google.com). Both are distributed under the **SIL Open Font License 1.1 (OFL-1.1)**.

| Font | Designer | License |
|------|----------|---------|
| [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) | CodeMan38 | [OFL-1.1](https://scripts.sil.org/OFL) |
| [Share Tech Mono](https://fonts.google.com/specimen/Share+Tech+Mono) | Igino Marini | [OFL-1.1](https://scripts.sil.org/OFL) |

By using Google Fonts, your browser may connect to Google servers. Refer to [Google's Privacy Policy](https://policies.google.com/privacy) for details.

---

### 3. Game Titles & Intellectual Property

The game titles, names, logos, and descriptions included in the dataset are the **intellectual property of their respective developers, publishers, and rights holders**. They are listed here strictly for **informational, educational, and non-commercial purposes** under the principles of fair use / fair dealing.

This project is:
- **not affiliated** with any game developer or publisher;
- **not commercial** — no advertising, no monetization, no game assets included;
- a **fan-curated editorial reference**, similar in nature to a bibliography or a catalogue.

All trademarks belong to their respective owners.

---

### 4. Audio

The background audio file (`z.mp3`) is used solely for aesthetic/atmospheric purposes in this non-commercial project. If you are the rights holder and wish to request removal or proper credit, please [open an issue](https://github.com/dskies/pixelDB/issues).

---

### 5. Dataset / Editorial Content

The editorial descriptions (`note` column) are **original writing** by the author and are covered by the MIT License.

The **factual data** (titles, years, genres) is non-copyrightable factual information. The **selection and arrangement** of the dataset is an original creative work by the author.

---

## Privacy

This project is a **fully static web application**. It does not:
- collect, store, or transmit any personal data;
- use cookies;
- include any analytics or tracking code.

Network requests are limited to:
- Google Fonts CDN (typeface files);
- The same origin (CSV data files).

---

## License

```
MIT License

Copyright (c) 2024–2026 dskies

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

*Last updated: April 2026*
