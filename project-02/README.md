# Boston Marathon 2017 — Mini-Project 02

> Sebastian Siedler — ssiedler3117@floridapoly.edu

## Project Purpose

This mini-project explores the 2017 Boston Marathon finisher results to understand how age, gender, and country of registration relate to marathon performance, and to identify behavioral patterns in finish time distributions.

---

## Dataset

| Property | Value |
|---|---|
| **File** | `../data/marathon_results_2017.csv` |
| **Rows** | 26,410 finishers |
| **Key columns** | Name, Age, Gender (M/F), Country, Official Time, Pace, 5K–40K split times |
| **Spatial data** | Natural Earth shapefiles in `../data/ne_110m_admin_0_countries/` |
| **Notes** | Finishers only (no DNF/DNS); country codes are non-standard and required manual remapping |

---

## Folder Structure

```
project-02/
├── siedler_project_02.Rmd      # Source RMarkdown — edit here
├── siedler_project_02.html     # Knitted HTML output
├── siedler_project_02.md       # Knitted Markdown (renders on GitHub)
├── siedler_project_02_files/   # Auto-generated figure assets
└── README.md                   # This file
```

---

## Software and Package Requirements

- **R** ≥ 4.0
- **tidyverse** — data wrangling and ggplot2
- **plotly** — interactive histograms
- **lubridate** — time string parsing
- **sf** — spatial data for choropleth
- **countrycode** — ISO country code conversion
- **broom** — tidy model output

Install with:

```r
install.packages(c("tidyverse", "plotly", "lubridate", "sf", "countrycode", "broom"))
```

---

## Reproducing the Analysis

1. Open `dataviz_final_project.Rproj` in RStudio
2. Navigate to `project-02/siedler_project_02.Rmd`
3. Click **Knit** (or run from the console):
   ```r
   rmarkdown::render("project-02/siedler_project_02.Rmd")
   ```
4. Output will appear as `siedler_project_02.html` and `siedler_project_02.md` in the same folder

---

## Summary of Findings

- **Age distribution** peaks around 40 — consistent with the Boston qualifying standard, which selects for experienced runners rather than first-timers
- **Psychological barriers** are clearly visible in the finish time histogram: spikes just before 3h and 4h are substantially larger than neighboring bins, reflecting goal-directed pacing
- **International runners** are faster on average than US-based runners, explained by selection bias: those who travel internationally to race tend to be more dedicated and faster
- **Performance peaks** in the mid-20s to mid-30s and declines gradually with age; the gender gap is consistent at ~30 minutes across all ages
- **Linear model** (`time ~ age + gender`): each additional year of age adds ~0.56 minutes; being female relative to male adds ~28 minutes

---

## Visualizations

1. Interactive histograms of age and finish time distributions (plotly)
2. Choropleth map of average finish time by country (sf / Natural Earth)
3. Annotated histogram of finish times with sub-3h / sub-4h markers
4. Median finish time by age and gender with loess smooth and annotated gap
5. Linear model coefficient plot with 95% confidence intervals

---

## Favorite Chart

The choropleth map (Visualization 2) is the most visually striking chart in this project. It communicates a non-obvious finding — international runners outperform US runners — at a glance, without any prior knowledge of the dataset. The blue/orange diverging palette centered on the global average makes the directional comparison immediate.

<img src="siedler_project_02_files/figure-html/spatial-choropleth-1.png" width="80%">

