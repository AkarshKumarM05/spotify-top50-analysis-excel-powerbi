# 📐 DAX Measures — Spotify Top 50 Power BI Dashboard

All **21 custom DAX measures** used in the Spotify Top 50 Global Power BI dashboard, organized into 6 categories.

---

## 📊 1. Core KPIs

### Total Distinct Songs
```dax
Total Distinct Songs = DISTINCTCOUNT('spotify-top-50-world'[track_name])
```

### Total Artists
```dax
Total Artists = DISTINCTCOUNT('spotify-top-50-world'[artist_name])
```

### Average Duration (Minutes)
```dax
Avg Duration Min = AVERAGE('spotify-top-50-world'[duration_ms]) / 60000
```

### Average Popularity Score
```dax
Avg Popularity = AVERAGE('spotify-top-50-world'[popularity])
```

### Total Streams
```dax
Total Streams = SUM('spotify-top-50-world'[streams])
```

---

## 🎵 2. Song & Album Analysis

### Songs by Album Type
```dax
Songs by Album Type =
CALCULATE(
    DISTINCTCOUNT('spotify-top-50-world'[track_name]),
    ALLEXCEPT('spotify-top-50-world', 'spotify-top-50-world'[album_type])
)
```

### Single Count
```dax
Single Count =
CALCULATE(
    COUNT('spotify-top-50-world'[track_name]),
    'spotify-top-50-world'[album_type] = "Single"
)
```

### Album Count
```dax
Album Count =
CALCULATE(
    COUNT('spotify-top-50-world'[track_name]),
    'spotify-top-50-world'[album_type] = "Album"
)
```

### Top Song by Streams
```dax
Top Song by Streams =
CALCULATE(
    MAX('spotify-top-50-world'[track_name]),
    TOPN(1, 'spotify-top-50-world', 'spotify-top-50-world'[streams], DESC)
)
```

---

## 🔞 3. Explicit Content Measures

### Explicit Track Count
```dax
Explicit Track Count =
CALCULATE(
    COUNT('spotify-top-50-world'[track_name]),
    'spotify-top-50-world'[explicit] = "Yes"
)
```

### Explicit Track %
```dax
Explicit Track % =
DIVIDE(
    CALCULATE(
        COUNT('spotify-top-50-world'[track_name]),
        'spotify-top-50-world'[explicit] = "Yes"
    ),
    COUNT('spotify-top-50-world'[track_name]),
    0
) * 100
```

### Non-Explicit Count
```dax
Non-Explicit Count =
CALCULATE(
    COUNT('spotify-top-50-world'[track_name]),
    'spotify-top-50-world'[explicit] = "No"
)
```

---

## 📅 4. Time Intelligence

### Streams by Month
```dax
Streams by Month =
CALCULATE(
    SUM('spotify-top-50-world'[streams]),
    ALLEXCEPT('spotify-top-50-world', 'spotify-top-50-world'[released_month])
)
```

### Streams by Quarter
```dax
Streams by Quarter =
CALCULATE(
    SUM('spotify-top-50-world'[streams]),
    ALLEXCEPT('DateTable', 'DateTable'[Quarter])
)
```

### Songs Released This Year
```dax
Songs This Year =
CALCULATE(
    COUNT('spotify-top-50-world'[track_name]),
    'spotify-top-50-world'[released_year] = YEAR(TODAY())
)
```

### Avg Popularity by Month
```dax
Avg Popularity by Month =
CALCULATE(
    AVERAGE('spotify-top-50-world'[popularity]),
    ALLEXCEPT('spotify-top-50-world', 'spotify-top-50-world'[released_month])
)
```

---

## 👑 5. Artist Performance

### Top Artist by Song Count
```dax
Top Artist by Song Count =
CALCULATE(
    MAX('spotify-top-50-world'[artist_name]),
    TOPN(
        1,
        SUMMARIZE(
            'spotify-top-50-world',
            'spotify-top-50-world'[artist_name],
            "SongCount", COUNT('spotify-top-50-world'[track_name])
        ),
        [SongCount], DESC
    )
)
```

### Top Artist by Streams
```dax
Top Artist by Streams =
CALCULATE(
    MAX('spotify-top-50-world'[artist_name]),
    TOPN(
        1,
        SUMMARIZE(
            'spotify-top-50-world',
            'spotify-top-50-world'[artist_name],
            "TotalStreams", SUM('spotify-top-50-world'[streams])
        ),
        [TotalStreams], DESC
    )
)
```

### Artist Avg Popularity
```dax
Artist Avg Popularity =
CALCULATE(
    AVERAGE('spotify-top-50-world'[popularity]),
    ALLEXCEPT('spotify-top-50-world', 'spotify-top-50-world'[artist_name])
)
```

---

## 🗓️ 6. Date Table DAX

### Generate Date Table
```dax
DateTable =
GENERATESERIES(
    DATE(2022, 1, 1),
    DATE(2024, 12, 31),
    1
)
```

### Calculated Columns on DateTable
```dax
Year = YEAR('DateTable'[Date])
Month = FORMAT('DateTable'[Date], "MMMM")
MonthNum = MONTH('DateTable'[Date])
Quarter = "Q" & QUARTER('DateTable'[Date])
```

---

## ✅ All 21 Measures Summary

| # | Measure Name | Category |
|---|-------------|----------|
| 1 | Total Distinct Songs | Core KPI |
| 2 | Total Artists | Core KPI |
| 3 | Avg Duration Min | Core KPI |
| 4 | Avg Popularity | Core KPI |
| 5 | Total Streams | Core KPI |
| 6 | Songs by Album Type | Album |
| 7 | Single Count | Album |
| 8 | Album Count | Album |
| 9 | Top Song by Streams | Album |
| 10 | Explicit Track Count | Explicit |
| 11 | Explicit Track % | Explicit |
| 12 | Non-Explicit Count | Explicit |
| 13 | Streams by Month | Time |
| 14 | Streams by Quarter | Time |
| 15 | Songs This Year | Time |
| 16 | Avg Popularity by Month | Time |
| 17 | Top Artist by Song Count | Artist |
| 18 | Top Artist by Streams | Artist |
| 19 | Artist Avg Popularity | Artist |
| 20 | Year / Month / Quarter columns | Date Table |
| 21 | DateTable (Generated) | Date Table |
