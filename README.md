JioSaavn Music Analytics Dashboard (Power BI)

Dashboard Link: https://app.powerbi.com/view?r=eyJrIjoiNzlkYmI0NTEtMDBmMS00NzhmLTgxMGItZGFmZjUwYmFhMzEyIiwidCI6IjIzODk2NDkwLTdlNzMtNGQ1Zi1hZjQ5LTBmMjUwMzQ5NWQ3NSJ9

Dashboard Overview

This project showcases a **JioSaavn Music Analytics Dashboard** developed using **Power BI**, with a **CSV file as the data source**. The dashboard analyzes music streaming data to provide insights into songs, artists, albums, popularity, and listening trends.

A key visual feature of this dashboard is the use of **image URLs** to dynamically display **album cover art**, enhancing user experience and making the report more engaging.

The report contains **one interactive dashboard page**, designed to present all insights in a single consolidated view.

---

Problem Statement

Music streaming platforms generate large volumes of metadata related to songs, artists, albums, and user engagement. The goal of this project is to transform raw CSV-based music data into a visually rich and analytical dashboard that allows users to:

* Analyze song and artist popularity
* Track streaming trends and engagement metrics
* Visually explore albums using cover images
* Evaluate performance using multiple KPIs powered by DAX

---

Tools & Technologies Used

* **Power BI Desktop**
* **CSV File (Data Source)**
* **DAX (Data Analysis Expressions)**
* **Image URL integration**
* **Single-page dashboard design**
* **Music analytics domain**

---

Steps Followed

### Data Preparation

* **Step 1:** Imported JioSaavn music data from a **CSV file** into Power BI.
* **Step 2:** Validated and formatted song, artist, album, and popularity fields.
* **Step 3:** Configured the album cover column as **Image URL** to render album artwork in visuals.

### Report Design

* **Step 4:** Designed a **single-page dashboard** to display all KPIs and insights.
* **Step 5:** Created multiple visuals to analyze songs, artists, albums, and popularity metrics.
* **Step 6:** Added KPI cards to highlight key music performance indicators.
* **Step 7:** Applied filters and slicers for interactive exploration.

---

DAX Measures Used (Copy–Paste Ready)

> This project uses **29 DAX measures**.
> Below are the **core and commonly used measures**, written exactly as they appear in the **Power BI Edit pane**.

---

Core Music Measures

```DAX
Total Songs =
DISTINCTCOUNT ( Music[Song_ID] )
```

```DAX
Total Artists =
DISTINCTCOUNT ( Music[Artist_Name] )
```

```DAX
Total Albums =
DISTINCTCOUNT ( Music[Album_Name] )
```

```DAX
Total Streams =
SUM ( Music[Stream_Count] )
```

---

### Popularity & Engagement Measures

```DAX
Average Popularity =
AVERAGE ( Music[Popularity] )
```

```DAX
Max Popularity =
MAX ( Music[Popularity] )
```

```DAX
Min Popularity =
MIN ( Music[Popularity] )
```

```DAX
Top Song Streams =
MAX ( Music[Stream_Count] )
```

---

### Artist & Album Measures

```DAX
Streams by Artist =
[Total Streams]
```

```DAX
Streams by Album =
[Total Streams]
```

```DAX
Average Streams per Song =
DIVIDE ( [Total Streams], [Total Songs], 0 )
```

```DAX
Songs per Album =
DIVIDE ( [Total Songs], [Total Albums], 0 )
```

---

### Ranking & Contribution Measures

```DAX
Song Rank by Streams =
RANKX (
    ALL ( Music[Song_Name] ),
    [Total Streams],
    ,
    DESC
)
```

```DAX
Artist Rank by Streams =
RANKX (
    ALL ( Music[Artist_Name] ),
    [Total Streams],
    ,
    DESC
)
```

```DAX
Stream Contribution % =
DIVIDE (
    [Total Streams],
    CALCULATE ( [Total Streams], ALL ( Music ) ),
    0
)
```

---

### KPI & Dashboard Measures

```DAX
Average Songs per Artist =
DIVIDE ( [Total Songs], [Total Artists], 0 )
```

```DAX
Top Album Streams =
MAX ( Music[Stream_Count] )
```

```DAX
Average Album Popularity =
AVERAGE ( Music[Popularity] )
```

```DAX
Most Popular Song =
SELECTEDVALUE ( Music[Song_Name] )
```

> Remaining measures follow similar DAX patterns to support filtering, ranking, and KPI calculations across the dashboard.

---

Special Features

* **Album cover images** displayed using URL-based image rendering
* Clean, modern single-page layout
* Interactive filtering for artist, album, and song-level analysis

---

Key Insights

* Identifies top-performing songs and artists based on streams.
* Highlights popularity distribution across albums.
* Visual album covers improve exploratory analysis and engagement.
* Single-page design allows quick consumption of music insights.

---

Conclusion

This JioSaavn Music Analytics Dashboard demonstrates strong skills in **Power BI DAX development**, **single-page dashboard design**, and **URL-based image integration**. The project effectively converts raw music metadata into an interactive and visually engaging analytics solution.
