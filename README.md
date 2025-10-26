# Posture Data Simulation and Analysis

## Overview
This script generates synthetic posture data over a defined period and computes various statistical summaries and performance scores related to body posture.  
It includes functions for analyzing pitch and roll angles, determining good/bad posture, classifying the cause of poor posture, and generating daily summary metrics.  
Additionally, it provides a plotting function (`plot_posture_data_grouped`) that the frontend (e.g., a website) can call to visualize posture trends over selectable timeframes.

---

## Features
- **Synthetic Data Generation**
  - Randomized pitch and roll data representing sensor readings.
  - Random timestamps over a configurable date range.
  
- **Posture Classification**
  - Determines posture as `good` or `bad` based on pitch and roll thresholds.
  - Identifies specific causes of bad posture: `pitch`, `roll`, or `both`.

- **Daily Summaries**
  - Aggregates daily means, standard deviations, minima, and maxima for pitch and roll.
  - Computes daily percentages of good and bad posture.
  - Computes detailed breakdowns of bad posture causes per day.

- **Scoring System**
  - Combines multiple posture metrics into a single **posture score (1–10)**:
    - Percentage of good posture (logistic scaling)
    - Pitch/Roll variance stability
    - Pitch/Roll mean deviation from neutral
    - Relative frequency of dual (“both”) bad causes

- **Visualization**
  - `plot_posture_data_grouped()` generates Matplotlib bar charts for:
    - Good vs Bad posture percentages, or  
    - Breakdown of bad posture causes (Pitch / Roll / Both)
  - Configurable by timeframe (`1`, `7`, or `30` days) and chart type.
  - Returns either a Matplotlib figure or an in-memory PNG buffer (for web serving).

---
## Authors
-  Colin
-  Rithvik
-  Enes
-  Varun

## Dependencies
Install the required Python libraries:
```bash
pip install numpy pandas matplotlib
