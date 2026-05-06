# Seasonal Affective Streaming

An independent data visualisation project exploring whether seasonal change appears in Spotify listening patterns. The analysis compares Spotify Top 200 tracks from 2021-2022 across Northern and Southern Hemisphere countries, using weighted audio-feature summaries to test whether local winters and summers are reflected in musical mood.

The central idea is simple: culture sets each country's baseline listening mood, while geography appears to shape the size and timing of its seasonal swing.

## View The Report

Open the rendered report directly from this repository:

- `seasonal-affective-streaming.html`

If GitHub Pages is enabled, `index.html` redirects to the report automatically.

## Project Outputs

- `seasonal-affective-streaming.qmd` contains the full Quarto analysis.
- `seasonal-affective-streaming.html` is the rendered self-contained report.
- `index.html` redirects to the rendered report for GitHub Pages.

## Highlights

- Cleans and aggregates track-level Spotify chart data into country-week summaries.
- Compares Northern and Southern Hemisphere seasonal patterns.
- Uses stream-weighted averages so higher-streamed tracks have more influence.
- Removes the Christmas/New Year period to reduce holiday music distortion.
- Builds exploratory and explanatory visualisations including:
  - country valence distributions
  - seasonal audio feature comparisons
  - monthly heatmaps
  - an interactive hemisphere time-series chart
  - a summer-vs-winter dumbbell plot
  - a choropleth seasonal swing map
  - a latitude regression chart

## Data

The raw dataset is intentionally not committed because it is large. To reproduce the report, place the Spotify CSV at:

```text
Data/spotify_data.csv
```

The expected columns include `country`, `week`, `streams`, `valence`, `energy`, and `acousticness`.

## Reproducing The Report

Install the required R packages:

```r
install.packages(c(
  "tidyverse",
  "lubridate",
  "hexbin",
  "plotly",
  "crosstalk",
  "htmltools",
  "ggrepel",
  "sf",
  "rnaturalearth",
  "rnaturalearthdata"
))
```

Render the Quarto file:

```bash
quarto render seasonal-affective-streaming.qmd
```

## GitHub Pages

To publish the report as a project page:

1. Open the repository settings.
2. Go to **Pages**.
3. Set the source to the main branch and root folder.
4. Open the generated Pages URL. It will load `index.html`, which redirects to `seasonal-affective-streaming.html`.

## Repository Notes

This repo is designed to show the final analysis clearly without committing local R sessions, installed packages, scratch files, or large raw data.
