# 🎵 Spotify Top 50 Global — Power BI Dashboard

![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Spotify](https://img.shields.io/badge/Spotify-1DB954?style=for-the-badge&logo=spotify&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-Measures-blue?style=for-the-badge)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)

> An end-to-end data analytics project analyzing Spotify’s Top 50 Global songs using Power BI, Excel, and 21 custom DAX measures with a custom background designed in Figma.

---

## 📌 Project Overview

This project explores the **Spotify Top 50 Global** dataset to uncover trends in:
- Song popularity and streaming behavior
- Artist dominance and song counts
- Album types (Single / Album / EP)
- Explicit content analysis
- Monthly and quarterly release trends

The dashboard was built in **Power BI Desktop** with a custom **Figma-designed background** and **21 DAX measures**.

---

## 🗂️ Folder Structure

```
spotify-top50-analysis-excel-powerbi/
│
├── 📁 assets/              ← Dashboard screenshots
├── 📁 dashboard/           ← Power BI .pbix file
├── 📁 data/                ← Raw CSV dataset
├── 📁 dax-measures/        ← All 21 DAX measures documented
└── README.md
```

---

## 📊 Dashboard Pages

| Page | Description |
|------|-------------|
| 🏠 **Home** | Custom Figma landing page with navigation |
| 📈 **Overview** | KPIs — total songs, artists, avg duration, avg popularity |
| 🎤 **Artist Analysis** | Top artists by song count and streams |
| 📅 **Trend Analysis** | Monthly & quarterly popularity trends |

---

## 📁 Dataset Columns

| Column | Description |
|--------|-------------|
| `track_name` | Name of the song |
| `artist_name` | Artist(s) name |
| `artist_count` | Number of artists on the track |
| `released_year` | Year released |
| `released_month` | Month released |
| `released_day` | Day released |
| `in_spotify_playlists` | Number of playlists featuring the song |
| `streams` | Total stream count |
| `bpm` | Beats per minute |
| `explicit` | Explicit content flag (Yes/No) |
| `album_type` | Single / Album / EP |

---

## 🔑 Key Insights

- 🏆 **Taylor Swift** dominates with the highest song count in Top 50
- 🎸 **Arctic Monkeys** leads in total stream count
- 📅 Popularity peaks between **January – March** each year
- 🎵 **Singles** make up the majority of chart entries
- 🔞 Explicit tracks tend to have **higher average stream counts**

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Dashboard building & visualization |
| **Microsoft Excel** | Data cleaning & preprocessing |
| **DAX** | 21 custom KPI measures |
| **Figma** | Custom dashboard background design |

---

## 📐 DAX Measures

All 21 DAX measures are fully documented in [`dax-measures/measures.md`](./dax-measures/measures.md)

Categories covered:
- 📊 Core KPIs (Songs, Artists, Streams, Popularity)
- 🎵 Song & Album Analysis
- 🔞 Explicit Content Measures
- 📅 Time Intelligence (Monthly, Quarterly)
- 👑 Artist Performance
- 🗓️ Date Table DAX

---

## 🚀 How to Use

```bash
git clone https://github.com/AkarshKumarM05/spotify-top50-analysis-excel-powerbi.git
```

1. Open `dashboard/Spotify_Top50_Dashboard.pbix` in **Power BI Desktop**
2. Connect data source to `data/spotify-top-50-world.csv`
3. Explore all 4 interactive dashboard pages

---

## 👨‍💻 Author

**Akarsh Kumar**
B.Com (Hons) | Data Analytics Enthusiast

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/akarshkumarm05/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AkarshKumarM05)

---

> ⭐ If you found this project useful, please give it a star — it helps a lot!
