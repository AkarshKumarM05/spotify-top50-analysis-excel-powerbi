# 🎵 Spotify Top 50 Global — Power BI Dashboard

![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Spotify](https://img.shields.io/badge/Spotify-1DB954?style=for-the-badge&logo=spotify&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-Measures-blue?style=for-the-badge)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)

> An end-to-end data analytics project analyzing Spotify's Top 50 Global songs using Power BI, Excel, and 21 custom DAX measures with a custom background designed in Figma.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Business Problem](#-business-problem)
- [Dataset](#-dataset)
- [Tools & Technologies](#%EF%B8%8F-tools--technologies)
- [Project Structure](#%EF%B8%8F-project-structure)
- [Data Cleaning & Preparation](#-data-cleaning--preparation)
- [Exploratory Data Analysis (EDA)](#-exploratory-data-analysis-eda)
- [Research Questions & Key Insights](#-research-questions--key-insights)
- [Dashboard](#-dashboard)
- [How to Run This Project](#-how-to-run-this-project)
- [Final Recommendations](#-final-recommendations)
- [Author & Contact](#-author--contact)

---

## 📖 Overview

This project explores the **Spotify Top 50 Global** dataset (2023–2024) to uncover meaningful trends in music streaming behavior. The goal is to help music analysts, playlist managers, and marketing teams make data-driven decisions by visualizing song and artist performance across multiple dimensions.

The dashboard was built in **Power BI Desktop** with a custom **Figma-designed background** and **21 DAX measures**, covering:

- Song popularity and streaming behavior
- Artist dominance and song counts
- Album types (Single / Album / Compilation)
- Explicit vs. Non-Explicit content performance
- Monthly and quarterly popularity trends

---

## 💼 Business Problem

Spotify's raw Top 50 dataset is limited to plain lists and rankings, making it difficult for stakeholders to identify patterns and extract insights quickly. This project addresses the following business challenges:

- **No KPI monitoring** — Stakeholders lack a quick summary of key metrics like total songs, distinct artists, average popularity, and average duration.
- **No explicit vs. non-explicit analysis** — It's unclear how explicit content performs compared to non-explicit in terms of popularity.
- **Difficulty tracking album/single distribution** — No visual breakdown by album type or release year exists.
- **Missing trend visibility** — Popularity trends and distinct song counts over time (monthly/quarterly) are not tracked.
- **Disconnected artist vs. song insights** — There is no drill-down capability linking high-level overviews to artist or song-level detail.
- **Decision-making gaps** — Marketing and curation teams cannot easily identify which artists or songs to promote or which content resonates most with audiences.

---

## 📁 Dataset

- **Source:** Spotify Top 50 Global Chart (2023–2024)
- **File:** `data/spotify-top-50-world.csv`
- **Rows:** ~28,000+ daily chart entries
- **Date Range:** December 2023 – November 2024

| Column | Description |
|---|---|
| `date` | Date of chart entry |
| `position` | Chart position (1–50) |
| `song` | Name of the song |
| `artist` | Artist(s) name |
| `popularity` | Spotify popularity score (0–100) |
| `durationms` | Track duration in milliseconds |
| `albumtype` | Single / Album / Compilation |
| `totaltracks` | Number of tracks in the album |
| `releasedate` | Original release date |
| `isexplicit` | Explicit content flag (True/False) |
| `albumcoverurl` | URL to album artwork |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard building & interactive visualization |
| **Microsoft Excel** | Data cleaning, preprocessing & exploration |
| **DAX** | 21 custom KPI and analytical measures |
| **Figma** | Custom dashboard background & UI design |
| **GitHub** | Version control & project documentation |

---

## 🗂️ Project Structure

```
spotify-top50-analysis-excel-powerbi/
│
├── 📁 assets/              ← Dashboard screenshots & visuals
├── 📁 dashboard/           ← Power BI .pbix file
├── 📁 data/                ← Raw CSV dataset
├── 📁 dax-measures/        ← All 21 DAX measures documented
└── README.md
```

---

## 🧹 Data Cleaning & Preparation

Before building the dashboard, the raw dataset was cleaned and structured in **Microsoft Excel**:

- Removed duplicate chart entries for the same song on the same date
- Standardized artist names with special characters (e.g., accented letters)
- Converted `durationms` to minutes format for readability
- Parsed `releasedate` into separate Year and Month columns for time intelligence
- Handled missing or null values in `popularity` and `albumtype` fields
- Created a dedicated **Date Table** in Power BI using DAX for accurate time-based filtering

---

## 🔍 Exploratory Data Analysis (EDA)

### Chart Coverage
- Dataset spans **December 2023 to November 2024** — over 11 months of daily Top 50 data
- Total of **789 distinct songs** appeared in the chart across this period
- **342 distinct artists** contributed to the Top 50

### Popularity Distribution
- Average popularity score across all entries: **~90 out of 100**
- Popularity peaks in **January–March** each year, likely driven by year-end award buzz and new releases
- Popularity dips slightly in **July–August**, corresponding to summer release saturation

### Album Type Breakdown
- **Singles** dominate chart entries — most hit songs are released as standalone singles
- **Albums** account for a significant portion, especially from Latin artists
- **Compilations** appear mostly in Christmas/holiday seasons (December charts)

### Explicit Content Analysis
- **~39% of songs** in the Top 50 are marked explicit
- Explicit tracks tend to appear more frequently in Top 10 positions
- Non-explicit tracks show broader appeal across demographics and longer chart stays

### Artist Concentration
- **Taylor Swift** leads with the highest number of distinct songs in the Top 50 (85 entries)
- **Travis Scott, Drake, Bad Bunny, Beyoncé** round out the top 5 most charting artists
- High concentration: Top 10 artists account for a disproportionate share of all chart appearances

---

## 💡 Research Questions & Key Insights

### 1. Who dominates the Spotify Top 50 globally?
**Finding:** Taylor Swift has the most chart appearances (85 songs), followed by Travis Scott (30) and Drake (27). This reflects the massive streaming power of established pop and rap artists.

### 2. Do explicit songs perform better?
**Finding:** Explicit tracks make up ~39% of the chart but tend to cluster in higher positions (Top 10). However, non-explicit tracks have longer chart lifespans, suggesting broader audience reach.

### 3. What album type dominates the charts?
**Finding:** Singles account for the majority of Top 50 entries. This aligns with modern music industry trends where artists release standalone singles to maximize streaming impact before full albums.

### 4. When is popularity highest throughout the year?
**Finding:** Average popularity is highest in **Q1 (January–March)**, driven by Grammy season buzz and New Year playlist refreshes. A secondary spike occurs in **Q4 (October–December)** due to holiday music.

### 5. Which songs had the most total streams (chart days)?
**Finding:** Songs like **"I Wanna Be Yours" (Arctic Monkeys)**, **"Cruel Summer" (Taylor Swift)**, and **"As It Was" (Harry Styles)** had the most cumulative chart days, indicating sustained long-term popularity rather than just viral spikes.

### 6. How does song duration relate to popularity?
**Finding:** Most Top 50 songs have an average duration of **~3.28 minutes**. Shorter tracks (under 3 minutes) are increasingly common in the streaming era, particularly in the rap and pop genres.

---

## 📊 Dashboard

The Power BI dashboard consists of **4 interactive pages**:

| Page | Description |
|---|---|
| 🏠 **Home** | Custom Figma-designed landing page with navigation buttons |
| 📈 **Overview** | KPIs — total songs, artists, avg duration, avg popularity; charts by album type, explicit content, month |
| 🎤 **Artist Analysis** | Top artists by song count; drill-down into artist-level songs, avg popularity, avg position |
| 🎵 **Songs Analysis** | Top songs by popularity; distribution by album type; detailed song table with release date & chart stats |

> Dashboard screenshots are available in the `assets/` folder.

---

## 🚀 How to Run This Project

### Prerequisites
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
- Microsoft Excel or any CSV viewer
- Git (optional, for cloning)

### Steps

**1. Clone the repository:**
```bash
git clone https://github.com/AkarshKumarM05/spotify-top50-analysis-excel-powerbi.git
```

**2. Navigate to the project folder:**
```bash
cd spotify-top50-analysis-excel-powerbi
```

**3. Open the dataset:**
- Locate `data/spotify-top-50-world.csv`
- Open in Excel to preview or verify data structure

**4. Open the Power BI Dashboard:**
- Open `dashboard/Spotify_Top50_Dashboard.pbix` in **Power BI Desktop**
- If prompted, update the data source path to point to `data/spotify-top-50-world.csv` on your local machine

**5. Refresh the data:**
- Go to **Home → Refresh** in Power BI Desktop to load the latest data

**6. Explore the dashboard:**
- Use the navigation buttons on the Home page to switch between Overview, Artist, and Songs pages
- Apply slicers to filter by artist, album type, explicit content, or time period

**7. View DAX Measures:**
- All 21 custom DAX measures are documented in `dax-measures/measures.md`

---

## ✅ Final Recommendations

Based on the analysis of Spotify's Top 50 Global chart data:

1. **Invest in single releases** — Singles dominate chart entries; labels and independent artists should prioritize single drops over full album releases for immediate streaming impact.

2. **Leverage Q1 momentum** — January to March sees peak popularity. New artist promotions and campaigns should be front-loaded into Q1 to capitalize on audience engagement.

3. **Don't ignore non-explicit content** — While explicit tracks rank highly, non-explicit songs show better longevity on the charts. Balancing both content types maximizes reach across demographics.

4. **Focus on repeat-charting artists** — Taylor Swift, Bad Bunny, and The Weeknd show consistent presence. Playlist curators should continue featuring these artists as anchor content.

5. **Optimize track duration** — Tracks under 3.5 minutes perform better in the streaming era. Artists and producers should consider shorter, hook-heavy compositions for chart targeting.

6. **Monitor Latin music growth** — Artists like Bad Bunny, Feid, Peso Pluma, and KAROL G show strong and growing global chart presence. Latin music represents a major opportunity for cross-genre promotion.

---

## 👨‍💻 Author & Contact

**Akarsh Kumar**
B.Com (Hons) | Data Analytics Enthusiast

## 👨‍💻 Author & Contact

**Akarsh Kumar**  
B.Com (Hons) | Data Analytics Enthusiast

[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:tulnama02@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/akarshkpandey)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AkarshKumarM05)

> ⭐ If you found this project useful, please give it a star — it helps a lot!
