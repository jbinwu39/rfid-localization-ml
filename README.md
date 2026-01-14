# RFID Grid Localization Using Average RSSI + Machine Learning (Capstone, 2022–2024)

- **Project type:** Undergraduate capstone (2-year scope)
- **My role:** TA / Project Advisor (2022–2024)
- **Core idea:** Use **per-antenna average RSSI** features to predict an RFID tag’s location on a **predefined 2D grid** (tag at ground level)
- **Best-performing model:** **k-Nearest Neighbors (KNN)**

---

## **Project Summary**

- Built a controlled RFID localization testbed and evaluated whether **machine learning is a viable tool** for localizing tags on a grid.
- Collected signal data from **four antennas** and aggregated readings into **average RSSI per antenna**.
- Expanded data collection to study sensitivity factors (e.g., **tag orientation** and **distance to antennas**).
- Benchmarked multiple models; **KNN** performed best under our feature representation.

---

## **Testbed Setup (Fall 2022 Pilot)**

- **Layout**
  - 4 RFID antennas positioned around a **table-top grid (mat)**
  - RFID tags placed at **ground level** on predefined grid points
- **Reference / Mapping**
  - Grid referenced using an **ArUco marker map** to maintain consistent locations across trials
- **Data collection**
  - Multiple reads per grid point, per antenna
  - Readings aggregated into summary features (average RSSI)

---

## **Project Timeline**

### **Year 1 (Fall 2022): Feasibility / Viability**
- **Goal**
  - Determine whether ML can localize an RFID tag on a predefined grid using RSSI measurements.
- **Outcome**
  - Demonstrated localization at multiple grid points on the mat, justifying expansion.

### **Year 2 (2023–2024): Data Collection + Sensitivity Factors**
- **Focus**
  - Improve dataset robustness and understand performance drivers.
- **Variables studied**
  - Tag orientation (**angle / rotation**)
  - Tag distance from each antenna
  - Repeatability across trials and collection protocols

---

## **Feature Engineering**

- **Input features (per sample)**
  - `avg_RSSI_antenna_1`
  - `avg_RSSI_antenna_2`
  - `avg_RSSI_antenna_3`
  - `avg_RSSI_antenna_4`
- **How features are formed**
  - Collect multiple reads at a grid point
  - Compute **average RSSI per antenna**
  - Use the resulting 4D vector as the ML input

---

## **Modeling Summary**

- **Problem framing**
  - Predict the RFID tag’s **grid location** on a predefined 2D mat using RSSI-based features.
- **Best model**
  - **k-Nearest Neighbors (KNN)** performed best in our benchmarks with per-antenna average RSSI features.

---

## **My Role (TA / Project Advisor, 2022–2024)**

- Guided teams on:
  - Experimental design and repeatable testing procedures
  - Data collection consistency and troubleshooting
  - Preprocessing and feature engineering (average RSSI per antenna)
  - Model evaluation and comparison practices
  - Documentation and project structure for reproducible work

---

## **Suggested Repository Structure**

- `data/`
  - Raw and/or processed datasets (or instructions if private/too large)
- `notebooks/`
  - EDA and baseline experiments
- `src/`
  - Preprocessing, feature extraction, and training/evaluation code
- `results/`
  - Figures, tables, metrics
- `docs/`
  - Setup photos, diagrams, notes

---

## **Notes / Limitations**

- RSSI-based localization is sensitive to:
  - Environmental multipath / interference
  - Tag orientation and placement
  - Antenna geometry and distance
- Results reflect a controlled grid testbed and are intended for capstone/educational demonstration.
