# DataZoba Frontend Engineering Assessment

This repository contains solutions for the DataZoba Frontend Engineering Fellowship assessment, covering data visualization tasks using D3.js and a story pitch for a data-driven narrative.

---

## Task 1 & 2: The Afrobeats Takeover 

**A scrollytelling data visualization showing how Afrobeats grew from a regional West African genre into a global music phenomenon between 2019–2024.**

![Afrobeats Takeover Preview](preview.png)

---

## Overview

In six years, Afrobeats went from Lagos to the world. This interactive data story visualizes monthly Spotify streams across 20 markets, revealing how a genre born in West Africa became the fastest-growing sound on the planet.

The visualization uses a **progressive line chart** tied to a narrative scroll experience. As readers move through six chapters — from "The Foundation" in 2019 to "The New Normal" in 2024 — the chart progressively reveals the data, showing how international streams caught up to and began overtaking African domestic streams.

---

## Features

### Progressive Data Reveal
The line chart unveils itself as users scroll through the narrative chapters. Each chapter corresponds to a year, and the chart's clip-path animates to reveal data up to that point in time. This creates a direct visual connection between the story being told and the data supporting it.

### Dual Market Visualization
Two distinct lines represent African markets (gold) and international markets (green), making the narrowing gap between them immediately visible. The color scheme is consistent throughout — from the chart lines to the legend, tooltips, and accent elements.

### Viral Song Markers
Key songs that drove the genre's global breakthrough — *Essence*, *Calm Down*, *Love Nwantiti*, *Last Last* — are plotted on the chart as interactive markers. Hovering reveals each song's Billboard chart performance and global reach. Marker size is proportional to Billboard chart presence.

### Interactive Tooltips
Hovering anywhere on the chart reveals:
- Exact monthly stream figures
- Market breakdown by country
- Nearest-line detection (automatically shows data for whichever market group is closest to the cursor)
- Contextual date formatting

### Responsive Design
Built with a fixed SVG `viewBox` for consistent rendering across screen sizes, with CSS Grid song cards that reflow on mobile. The sticky chart container keeps the visualization visible while scrolling through chapters.

### Editorial Design
Typography pairs DM Serif Display (headlines) with DM Sans (body), using a dark background with gold accents. Inline stat callouts within chapters reinforce key data points without pulling readers away from the narrative.

---

## Technologies

| Technology | Role |
|-----------|------|
| **D3.js v7** | Data binding, scales, line generation, SVG rendering, event handling |
| **IntersectionObserver API** | Scroll-driven chapter detection for progressive chart reveal |
| **CSS Custom Properties** | Theming and consistent color management |
| **SVG clipPath** | Animated line reveal tied to scroll position |
| **CSS Grid** | Responsive viral songs card layout |
| **Google Fonts** | DM Serif Display & DM Sans typography |

### Key D3 Techniques Used
- `d3.scaleLinear()` for both X (time) and Y (stream volume) axes
- `d3.line()` with `curveCatmullRom` for smooth line interpolation
- `d3.pointer()` for accurate hover coordinate detection
- SVG `clipPath` with animated `width` transitions for scroll-driven reveal
- Event delegation on overlay rectangles for efficient hover interaction

---

## Data Sources

### `afrobeats streams by country.csv`
**Structure:** Long-format CSV with one row per country per year.

| Column | Description |
|--------|-------------|
| `year` | Year of data (2019–2024) |
| `country` | Market name (e.g., Nigeria, USA, UK) |
| `continent` | Geographic continent |
| `monthly_streams_millions` | Estimated monthly Spotify streams in millions |
| `is_african_market` | "Yes" for African countries, "No" for international |

**Coverage:** 20 markets — 10 African (Nigeria, Ghana, Kenya, South Africa, Tanzania, Senegal, Cameroon, Côte d'Ivoire, plus 2 others) and 10 international (USA, UK, France, Germany, Canada, Brazil, Netherlands, plus 3 others).

### `afrobeats viral songs.csv`
**Structure:** One row per viral song.

| Column | Description |
|--------|-------------|
| `song` | Track title |
| `artist` | Primary artist(s) |
| `year` | Peak year |
| `peak_spotify_daily_global` | Highest daily global chart position |
| `tiktok_videos_millions` | Approximate TikTok video count using the sound (millions) |
| `weeks_on_billboard_hot100` | Weeks spent on Billboard Hot 100 |
| `countries_charted` | Number of countries where the song charted |
| `genre` | Sub-genre classification |

---

## Data Processing Pipeline

### 1. Raw Data → Structured Arrays
The CSV files are loaded using `d3.csv()`, which automatically parses rows into JavaScript objects with string values.

### 2. Annual → Monthly Distribution
Since the source data provides annual totals per country, the data is distributed across 12 months using this formula:

---

## Task 3: Remittance Story Pitch

### Overview

This task involved developing a story pitch for a data visualization focusing on remittance inflows to Sub-Saharan Africa. The core narrative aims to highlight the critical, yet often overlooked, role of remittances as a financial lifeline for many African economies and families.

### The Story

The pitch argues that remittances, totaling an estimated $54 billion in 2023, represent the most reliable financial support for Sub-Saharan Africa, often surpassing foreign direct investment and official development aid. It emphasizes the significant dependency of countries like Gambia, Lesotho, and Comoros on these inflows, where remittances can account for 20-35% of GDP. The narrative also explores the divergence in remittance trends across different African regions during the COVID-19 pandemic, showcasing how global crises impact diaspora giving.

### Dataset

-   **Primary Source**: World Bank Open Data — *Remittance Inflows to GDP (%) · Sub-Saharan Africa · 2000–2023*
    *   **URL**: https://data.worldbank.org/indicator/BX.TRF.PWKR.DT.GD.ZS
-   **Supplementary Data**: KNOMAD Remittance Data (Global Knowledge Partnership on Migration and Development)
-   **Coverage**: 48 Sub-Saharan African countries, annual figures, percentage of GDP and USD totals.

### Proposed Visualization

-   **Primary Chart**: A small-multiples area chart, with one panel per country (or region), illustrating remittance inflows as a percentage of GDP from 2000–2023. Countries would be arranged by remittance dependency.
-   **Overlay**: A dot annotation layer marking key global events (e.g., 2008 financial crisis, 2020 COVID lockdowns) to show how diaspora giving responds to external shocks.
-   **Interaction**: Clicking a country panel would expand it to a full-width view, revealing USD totals, top three source corridors, and average transfer fees (highlighting the "quietly devastating" cost of remittances).

### Target Audience & Impact

The story aims to engage:

-   **Policymakers**: To advocate for transfer fee regulation, demonstrating its direct impact on household income.
-   **Diaspora Communities**: To acknowledge and celebrate their significant, often unrecognized, contributions.
-   **Anyone who thinks about Africa**: To shift the dominant narrative from aid dependency to the continent's robust, family-driven financial infrastructure.

### Proposed Tools

-   **D3.js**: For precise control over chart geometry and data binding.
-   **Svelte**: For efficient state management and handling interactive elements like expand/collapse functionality.

---

## Future Enhancements

-   Implement the full country breakdown in the Afrobeats visualization tooltip using a more granular CSV.
-   Develop the small-multiples remittance chart as described in the Task 3 pitch, integrating D3.js and Svelte.
-   Add a loading indicator for the CSV data in the Afrobeats chart.
```
