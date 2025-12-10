# Spatial Health Risk Assessment in Sharjah Using GIS and Automated Python-Based Weighted Overlay

## Project Overview

This repository documents a project focused on developing and validating a spatial model to delineate cumulative environmental health risk zones in the Emirate of Sharjah, UAE. The study contrasts the outputs of a **manual GIS workflow** against an **automated Python (ArcPy) script** to assess the reliability and accuracy of spatial automation in environmental planning.

* [cite_start]**Study Area:** Emirate of Sharjah, UAE [cite: 199]
* [cite_start]**Core Method:** GIS-based Weighted Overlay Analysis [cite: 176]
* [cite_start]**Primary Goal:** Identify high-risk zones driven by multiple environmental stressors for targeted policy intervention[cite: 180, 297].

---

## 1. Problem Statement

[cite_start]Rapid urban growth in Sharjah has led to increased environmental stressors, including emissions from industries and transportation systems, especially near residential areas[cite: 174, 189]. [cite_start]While data on population, road networks, and industrial activity are available separately, their combined effect on health risk was not represented in a single integrated framework[cite: 194].

[cite_start]This project addresses this gap by creating a composite health risk index to clearly identify areas requiring priority monitoring and intervention strategies[cite: 195, 303].

---

## 2. Methodology: Weighted Health Risk Index

[cite_start]A **Weighted Overlay** technique was used to merge reclassified input layers into a final composite index[cite: 176, 192].

### Input Factors (Stressors)
[cite_start]The model integrated the following three primary factors, all reclassified into standardized impact levels (low, medium, and high)[cite: 176, 212]:
1.  [cite_start]**Population Density:** Derived from WorldPop data[cite: 205].
2.  [cite_start]**Industrial Activity:** Derived from Sharjah Municipality datasets[cite: 205].
3.  [cite_start]**Road Density:** Derived from major road datasets (ArcGIS and OpenStreetMap)[cite: 205].
[cite_start]*(Note: Initial planning also considered Aerosol Optical Depth (AOD) as a factor)[cite: 336].*

### Workflow Comparison
The study performed the Weighted Overlay using two distinct workflows:
1.  [cite_start]**Manual Workflow:** Implemented step-by-step in ArcGIS Pro[cite: 177, 211].
2.  [cite_start]**Automated Workflow:** Programmatically reproduced using a Python (ArcPy) script to perform all steps (conversion, reclassification, weighting, overlay) in a single run[cite: 177, 221].

---

## 3. Key Findings: Validation of Spatial Accuracy

[cite_start]The comparison revealed that the two workflows, despite sharing the same core logic, produced outputs with significant spatial differences, primarily due to parameter settings and aggregation issues in the automated script[cite: 287, 291].

### Final Risk Index Comparison

| Feature | Manual Weighted Overlay Output (e.g., `Health_Risk_Index1.png`) | Automated Python Output (e.g., `Health_Risk_Index2.png`) | Reliability Implication |
| :--- | :--- | :--- | :--- |
| **Spatial Pattern** | [cite_start]**Continuous & Coherent:** Shows a clear, continuous high-risk zone along the urban and coastal corridor, accurately reflecting clustered industry and roads[cite: 282, 292]. | [cite_start]**Fragmented & Scattered:** Displays isolated high-risk patches with large unclassified areas, failing to reflect the true regional pattern[cite: 284, 293]. | [cite_start]**Manual is More Realistic.** Fragmentation suggests issues with spatial aggregation in the script[cite: 293]. |
| **Value Range** | [cite_start]**Wide Dynamic Range:** Values range from **1.6 to 3.0**[cite: 281]. | [cite_start]**Narrow Range:** Values range from **2.0 to 2.4**[cite: 284]. | [cite_start]**Manual is More Actionable.** Narrow range in Python under-represents the true cumulative risk, masking severe exposure[cite: 285]. |
| **Population Input** | [cite_start]Accurate: Closely matches census data, showing population concentrated in small, isolated clusters in urban centers[cite: 271]. | [cite_start]Distorted: Displays sizable, continuous blocks of high density, which exaggerates population spread across the territory[cite: 272]. | [cite_start]**Manual is Ground-Truth Aligned.** Python input likely suffered from inappropriate reclassification parameters[cite: 275]. |

[cite_start]**Overall Conclusion:** The manual workflow produced the most accurate and dependable spatial patterns for defining high-risk zones that correspond with Sharjah's established distribution of stressors[cite: 294, 298]. [cite_start]The high-risk zones are concentrated along the main urban and coastal corridor[cite: 297].

---

## 4. Recommendations and Future Work

To fully leverage the efficiency of automation without compromising spatial accuracy, the following steps are recommended:

### I. Refine Automation Parameters
* [cite_start]**Action:** Directly embed the precise reclassification and weighting parameters from the validated Manual process into the Python script[cite: 301, 302].
* [cite_start]**Goal:** Resolve parameter-sensitivity issues and ensure the automated output achieves the spatial accuracy of the manual maps[cite: 301].

### II. Enhance Model Inputs
* [cite_start]**Action:** Integrate additional environmental stressors, such as **real air-quality measurements** or detailed **land-use data**, in future stages[cite: 305].
* [cite_start]**Goal:** Improve the model's predictive power and provide a more comprehensive risk assessment[cite: 305].

### III. Policy Application
* [cite_start]**Action:** Utilize the high-accuracy manual output to prioritize **environmental monitoring** and **public health resource allocation** in the designated high-risk zones (close to industrial areas and busy roads)[cite: 303].

---

## 5. Repository Files

| File Name | Description | Source Reference (Programming Document) |
| :--- | :--- | :--- |
| `programming project .docx` | Full project report, methodology, and detailed comparison analysis (Abstract, Sections 1-9). [cite_start]| [cite: 170-320] |
| `Milestone1_Aldarmaki_Maitha..pdf` | Initial project proposal and problem definition. [cite_start]| [cite: 321-338] |
| `Health_Risk_Index1.png` / `ArcGIS1.png` | **Validated Final Map:** Health Risk Index from the Manual/Software workflow (Value 1.6-3.0). | [cite_start]Figure 4/5 [cite: 233, 234] |
| `Health_Risk_Index2.png` / `ArcPy1.png` | Automated Final Map: Health Risk Index from the Python script (Value 2.0-2.4). | [cite_start]Figure 7 [cite: 247] |
| `ArcGIS.png` | Reclassified Population Density Map (Manual/Accurate Input). | [cite_start]Figure 1 [cite: 216] |
| `ArcPy.png` | Reclassified Population Density Map (Python/Distorted Input). | [cite_start]Figure 4 (in comparison section) [cite: 264] |
| `Roads_density.png` | Road Density Layer (Input Factor). | [cite_start]Figure 3 [cite: 218] |
| `Screenshot 2025-12-06 at 6.59.36 pm.png` | Industrial Activity Reclassification Layer (Input Factor). | [cite_start]Figure 2 [cite: 217] |
| `new-census-chart-29Jan17b.png` | Sharjah 2015 Census Data (Ground-Truth Validation Reference). [cite_start]| [cite: 269] |
