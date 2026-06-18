# Boston Marathon 2017 — Data Visualization Mini-Project 2

> Sebastian Siedler — ssiedler3117@floridapoly.edu

## Motivation

I'm interested in running, so I chose the Boston Marathon 2017 dataset to explore how age, gender, and nationality affect marathon performance.

## Data

The dataset contains 26,000+ finishers from the 2017 Boston Marathon, including age, gender, origin (city/state/country), split times every 5K, pace, and official finishing time. Natural Earth shapefiles were used for the spatial visualization.

## Summary of Findings

- **Age distribution** peaks around 40; most finishers run between 3.5–4.5 hours.
- **Psychological barriers** cause visible spikes at round-number finish times (especially sub-4 hours).
- **International runners** are faster on average than US-based runners, likely because traveling abroad selects for more dedicated athletes.
- **Performance peaks** in the 20s–30s and declines gradually; the gender gap is consistent at ~30 minutes across all ages.
- **Linear model**: Each year of age adds ~0.56 minutes; being female adds ~28 minutes relative to male.

## Visualizations

1. Interactive histograms of age and finish time distributions (plotly)
2. Choropleth map of average finish time by country (sf / Natural Earth)
3. Annotated histogram of finish times with sub-3h / sub-4h markers
4. Median finish time by age and gender with loess smooth
5. Linear model coefficient plot with 95% confidence intervals
