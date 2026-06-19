# Mini-Project 01 — World Cup Matches (1930–2014)

> Sebastian Siedler — ssiedler3117@floridapoly.edu

## Project Purpose

This mini-project explores historical FIFA World Cup match data to answer three questions:

1. How has the average number of goals per match changed across tournaments?
2. Which national teams have been the most successful in terms of total wins?
3. How has average match attendance grown over the decades?

---

## Dataset

| Property | Value |
|---|---|
| **File** | `../data/WorldCupMatches.csv` |
| **Rows** | 852 matches (after filtering 3,720 blank rows) |
| **Time range** | 1930–2014 (20 tournaments) |
| **Key columns** | Year, Stage, Home/Away Team Name, Home/Away Team Goals, Attendance, City, Country |
| **Notes** | No tournaments in 1942 or 1946 (WWII); match counts per tournament grew from 18 (1930) to 64 (1998+) |

---

## Folder Structure

```
project-01/
├── siedler_project_01.Rmd      # Source RMarkdown — edit here
├── siedler_project_01.html     # Knitted HTML output
├── siedler_project_01.md       # Knitted Markdown (renders on GitHub)
├── siedler_project_01_files/   # Auto-generated figure assets
└── README.md                   # This file
```

The dataset lives in `../data/WorldCupMatches.csv` (one level up, in the shared `data/` folder).

---

## Software and Package Requirements

- **R** ≥ 4.0
- **tidyverse** — data wrangling and ggplot2
- **plotly** — interactive visualization

Install with:

```r
install.packages(c("tidyverse", "plotly"))
```

---

## Reproducing the Analysis

1. Open `dataviz_final_project.Rproj` in RStudio
2. Navigate to `project-01/siedler_project_01.Rmd`
3. Click **Knit** (or run from the console):
   ```r
   rmarkdown::render("project-01/siedler_project_01.Rmd")
   ```
4. Output will appear as `siedler_project_01.html` and `siedler_project_01.md` in the same folder

---

## Summary of Findings

- **Goals per match** peaked in the 1950s (>5 goals/match in 1954) and have declined to roughly 2.5–3.0 in the modern era, driven by tactical evolution, defensive specialization, and rule changes
- **Brazil** leads all nations in total World Cup wins (home + away combined), consistent with their five tournament titles; Germany/Germany FR combined ranks second
- **Attendance** has grown over time, with the 1994 US-hosted tournament showing the highest average per match — a reflection of large American stadium capacity
- The **WWII gap** (no tournaments 1942–1946) is clearly visible in the attendance chart and provides useful historical grounding

---

## Favorite Chart

The interactive plotly version of Visualization 1 (average goals per match over time) is the most informative single chart in this project. Hovering over each data point reveals the exact average, the match count, and the host country — context that would be impossible to include in a static chart without severely cluttering it.

<img src="siedler_project_01_files/figure-html/viz2-1.png" width="70%">
