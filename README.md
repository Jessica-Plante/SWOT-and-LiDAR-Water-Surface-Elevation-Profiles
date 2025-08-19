# Water Surface Elevation River Profile Visualization
---

## Overview

This Python script visualizes and compares water surface elevation (WSE) profiles derived from the SWOT mission across multiple acquisition dates. It also integrates LiDAR data and highlights the location of a known landslide. The script includes uncertainty bands (±RMSE) for each data source, allowing for visual inspection of measurement precision.

---

## What the Script Does

For each selected SWOT acquisition date:

* Loads WSE profile data from Excel files.
* Plots WSE profiles along longitude.
* Adds ±RMSE uncertainty bands based on validation results.
* Incorporates LiDAR data (May 20–21) with its own ±RMSE band.
* Highlights the landslide region with a gray hatched area.

---

##  Input Files

You must place the following Excel files in the specified locations:

1. **SWOT WSE profiles:**

   * `/content/SWOT_WSE_2024-07-12.xlsx`
   * `/content/SWOT_WSE_2024-08-02.xlsx`
   * `/content/SWOT_WSE_2024-08-13.xlsx`
   * `/content/SWOT_WSE_2024-09-08.xlsx`

2. **LiDAR and SWOT nodes:**

   * `/content/SWOT_vs_LiDAR_2024-05-20-21.xlsx`

Each Excel file must contain the following columns:

* `Longitude`: X-coordinate of the measurement (in decimal degrees).
* `WSE`: Water Surface Elevation (in meters).
* `data_type`: Must be one of `'raster'`, `'nodes'`, or `'LiDAR'`.

---

## Output

* A **multi-date plot** showing:

  * SWOT WSE profiles with unique colors, markers, and line styles.
  * ±RMSE bands per date.
  * LiDAR measurements and node profiles.
  * A gray hatched band representing the landslide area.

##  Dependencies

Install the required Python packages:

```bash
pip install pandas matplotlib numpy openpyxl
```

---

## Notes

* Files must have correct column names (`Longitude`, `WSE`, `data_type`).

---

