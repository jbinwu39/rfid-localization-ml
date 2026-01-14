RFID Grid Localization using Average RSSI + Machine Learning (Capstone Project, 2022–2024)

This repository contains materials from an undergraduate capstone project focused on RFID tag localization on a predefined 2D grid using machine learning and per-antenna average RSSI features. I supported the project as the TA / project advisor from 2022–2024, helping guide experimental design, data collection, and ML evaluation across multiple student teams.

Overview

RFID-based localization is challenging due to environmental noise, multipath effects, and sensitivity to tag placement and orientation. This project explored whether a practical, repeatable setup could localize a tag’s position on a grid using RSSI measurements collected from multiple antennas.

The workflow is:

Build a controlled testbed with known grid coordinates.

Collect RFID reads at each grid point across multiple trials.

Aggregate readings by computing average RSSI per antenna.

Train and evaluate ML models that map the RSSI feature vector to a predicted grid location.

Expand data collection to study sensitivity factors such as tag orientation and antenna distance.

Testbed Setup (Fall 2022 Pilot)

Physical layout: A table-top grid (mat) with four RFID antennas placed around the area.

Reference system: The test region was referenced using an ArUco marker map to maintain consistent and repeatable grid locations across trials.

Tag placement: Tags were placed at ground level on predefined grid points.

Measurements: For each grid point, multiple RFID readings were collected from each antenna.

Project Phases
Year 1 (Fall 2022): Feasibility / Viability of ML for Localization

The first year focused on a core feasibility question:

Is machine learning a viable tool to localize an RFID tag on a predefined grid using RSSI measurements from multiple antennas?

During this phase, the team established the testbed, developed a baseline data collection workflow, and evaluated models using per-antenna average RSSI as the primary feature representation. The pilot results showed that the system could localize tags at multiple grid points on the mat, motivating expansion to a larger and more systematic dataset.

Year 2 (2023–2024): Data Collection and Sensitivity Factors

The second year focused more heavily on data collection quality and understanding what conditions drive performance changes. Key factors studied included:

Tag orientation / angle (rotation)

Distance between the tag and each antenna

Repeatability across trials and collection protocols to reduce noise

The goal of this phase was to build a more robust dataset and to characterize when RSSI-based localization performs well versus when it degrades.

Feature Engineering

Primary feature representation:
For each grid point, we computed the average RSSI value from each antenna (after aggregating multiple reads). This produces a compact feature vector:

[avg_RSSI_antenna_1, avg_RSSI_antenna_2, avg_RSSI_antenna_3, avg_RSSI_antenna_4]

This approach reduces variance from individual reads and enables straightforward model benchmarking.

Modeling Summary

We benchmarked multiple ML approaches for predicting tag location on the grid. In our evaluation, k-Nearest Neighbors (KNN) consistently performed best for this problem formulation and feature representation (per-antenna average RSSI), and it became the primary baseline model.

My Role (TA / Project Advisor)

From 2022–2024, I supported the capstone teams by:

Guiding experimental design and defining repeatable data collection procedures

Supporting hardware/software troubleshooting during testbed setup

Advising on data preprocessing and feature engineering (average RSSI per antenna)

Helping teams structure model evaluation and compare approaches consistently

Providing feedback on documentation and presentation of results
