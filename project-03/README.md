# Project 03 — Tampa Weather & Concrete Strength

> Sebastian Siedler — ssiedler3117@floridapoly.edu

## Project Purpose

This project has two parts:

1. **Part 1 (Tampa weather):** Reproduce and extend density/distribution plots of daily maximum temperatures at Tampa International Airport (2022), and create an original precipitation visualization that highlights Florida's rainy season.
2. **Part 2 (Concrete strength):** Explore the UCI Concrete Compressive Strength dataset through distribution plots, a grouped boxplot by curing age, and a multi-variable scatterplot.

---

## Datasets

### Part 1 — Tampa International Airport Weather (2022)

| Property | Value |
|---|---|
| **Source** | [FSU Florida Climate Center](https://climatecenter.fsu.edu/climate-data-access-tools/downloadable-data) |
| **URL** | `https://raw.githubusercontent.com/aalhamadani/datasets/master/tpa_weather_2022.csv` |
| **Rows** | 365 daily observations |
| **Key columns** | year, month, day, max\_temp, min\_temp, precipitation |
| **Notes** | Sentinel values -99.9 (temperature) and -99.99 (precipitation) indicate missing data |

### Part 2 — UCI Concrete Compressive Strength

| Property | Value |
|---|---|
| **Source** | [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php) |
| **File** | `../data/concrete.csv` |
| **Rows** | 1,030 observations |
| **Key columns** | Cement, Water, Fly Ash, Slag, Superplasticizer, Coarse/Fine Aggregate, Age, Concrete\_compressive\_strength |

---

## Folder Structure

```
project-03/
├── siedler_project_03.Rmd      # Source RMarkdown — edit here
├── siedler_project_03.html     # Knitted HTML output
├── siedler_project_03.md       # Knitted Markdown (renders on GitHub)
├── siedler_project_03_files/   # Auto-generated figure assets
└── README.md                   # This file
```

---

## Software and Package Requirements

- **R** ≥ 4.0
- **tidyverse** — data wrangling and ggplot2
- **plotly** — interactive precipitation chart
- **lubridate** — date parsing for weather data
- **ggridges** — ridgeline density plots

Install with:

```r
install.packages(c("tidyverse", "plotly", "lubridate", "ggridges"))
```

---

## Reproducing the Analysis

1. Open `dataviz_final_project.Rproj` in RStudio
2. Navigate to `project-03/siedler_project_03.Rmd`
3. Click **Knit** (or run from the console):
   ```r
   rmarkdown::render("project-03/siedler_project_03.Rmd")
   ```
4. Output will appear as `siedler_project_03.html` and `siedler_project_03.md` in the same folder

Note: Part 1 loads the weather data directly from a GitHub URL — an active internet connection is required.

---

## Summary of Findings

**Part 1 — Tampa Weather:**
- Summer months (June–September) show narrow temperature distributions concentrated in the high 80s–low 90s °F, while winter months spread more widely across the 50s–70s °F range
- The ridgeline plot makes the seasonal progression from cool/variable to hot/consistent temperatures visually immediate
- July is the peak precipitation month (~14 inches total), and the June–September rainy season accounts for the majority of annual rainfall

**Part 2 — Concrete:**
- Compressive strength increases substantially with curing age, especially in the first 28 days
- Higher cement content and lower water content are both associated with higher strength — consistent with the water-to-cement ratio principle
- The spread within each age group is large, confirming that mix composition matters as much as curing time

---

## Favorite Chart

The precipitation bar chart (Part 1, section (e)) is the most purposeful original visualization in this project. By highlighting only the rainy season months in blue and graying everything else out, it directs the reader's attention without requiring a legend or annotation to explain the comparison.

<img src="siedler_project_03_files/figure-html/unnamed-chunk-10-1.png" width="80%">
