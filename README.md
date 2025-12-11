# Spatial Health Risk Assessment in Sharjah Using GIS and Automated Python-Based Weighted Overlay

## Project Overview

This repository documents a project focused on developing and validating a spatial model to delineate cumulative environmental health risk zones in the Emirate of Sharjah, UAE. The study contrasts the outputs of a **manual GIS workflow** against an **automated Python (ArcPy) script** to assess the reliability and accuracy of spatial automation in environmental planning.

* **Study Area:** Emirate of Sharjah, UAE 
* **Core Method:** GIS-based Weighted Overlay Analysis
* **Primary Goal:** Identify high-risk zones driven by multiple environmental stressors for targeted policy intervention.

---

## 1. Problem Statement

Rapid urban growth in Sharjah has led to increased environmental stressors, including emissions from industries and transportation systems, especially near residential areas[cite: While data on population, road networks, and industrial activity are available separately, their combined effect on health risk was not represented in a single integrated framework.

This project addresses this gap by creating a composite health risk index to clearly identify areas requiring priority monitoring and intervention strategies.

---

## 2. Methodology: Weighted Health Risk Index

A **Weighted Overlay** technique was used to merge reclassified input layers into a final composite index.

### Input Factors (Stressors)
The model integrated the following three primary factors, all reclassified into standardized impact levels (low, medium, and high):
1.  **Population Density:** Derived from WorldPop data.
2.  **Industrial Activity:** Derived from Sharjah Municipality datasets.
3.  **Road Density:** Derived from major road datasets (ArcGIS and OpenStreetMap).
(Note: Initial planning also considered Aerosol Optical Depth (AOD) as a factor).

### Workflow Comparison
The study performed the Weighted Overlay using two distinct workflows:
1.  **Manual Workflow:** Implemented step-by-step in ArcGIS Pro.
2.  **Automated Workflow:** Programmatically reproduced using a Python (ArcPy) script to perform all steps (conversion, reclassification, weighting, overlay) in a single run[cite:

---

## 3. Key Findings: Validation of Spatial Accuracy

The comparison revealed that the two workflows, despite sharing the same core logic, produced outputs with significant spatial differences, primarily due to parameter settings and aggregation issues in the automated script.

### Final Risk Index Comparison

| Feature | Manual Weighted Overlay Output | Automated Python Output | Reliability Implication |
| :--- | :--- | :--- | :--- |
| **Spatial Pattern** | **Continuous & Coherent:** Shows a clear, continuous high-risk zone along the urban and coastal corridor, accurately reflecting clustered industry and roads. | **Fragmented & Scattered:** Displays isolated high-risk patches with large unclassified areas, failing to reflect the true regional pattern. | **Manual is More Realistic.** Fragmentation suggests issues with spatial aggregation in the script |
| **Value Range** | **Wide Dynamic Range:** Values range from **1.6 to 3.0**. | **Narrow Range:** Values range from **2.0 to 2.4**. | **Manual is More Actionable.** Narrow range in Python under-represents the true cumulative risk, masking severe exposure. |
| **Population Input** | Accurate: Closely matches census data, showing population concentrated in small, isolated clusters in urban centers. | Distorted: Displays sizable, continuous blocks of high density, which exaggerates population spread across the territory. | **Manual is Ground-Truth Aligned.** Python input likely suffered from inappropriate reclassification parameters. |

**Overall Conclusion:** The manual workflow produced the most accurate and dependable spatial patterns for defining high-risk zones that correspond with Sharjah's established distribution of stressors. The high-risk zones are concentrated along the main urban and coastal corridor.

---

## 4. Recommendations and Future Work

To fully leverage the efficiency of automation without compromising spatial accuracy, the following steps are recommended:

### I. Refine Automation Parameters
* **Action:** Directly embed the precise reclassification and weighting parameters from the validated Manual process into the Python script.
* **Goal:** Resolve parameter-sensitivity issues and ensure the automated output achieves the spatial accuracy of the manual maps.

### II. Enhance Model Inputs
* **Action:** Integrate additional environmental stressors, such as **real air-quality measurements** or detailed **land-use data**, in future stages.
* **Goal:** Improve the model's predictive power and provide a more comprehensive risk assessment.

### III. Policy Application
* **Action:** Utilize the high-accuracy manual output to prioritize **environmental monitoring** and **public health resource allocation** in the designated high-risk zones (close to industrial areas and busy roads).

---

## 5. Repository Structure

The project files are organized into the following folders for clarity and ease of access:

| Folder / File Name | Description | Source Reference (Programming Document) |
| :--- | :--- | :--- |
| **Code/** | Contains the automated GIS script (Python Toolbox). | |
| ├── `healthrisktool.pyt` | **The Automated Tool:** Python Toolbox for ArcGIS Pro containing the logic for reclassification and weighted overlay. | |
| **Datasets/**| Contains the key input raster data used in the analysis. | |
| **Project_Presentation/** | Contains the slides used for defending the project. | |
| ├── `Project_Presentation.pdf` | The full slide deck summarizing the project, methodology, and findings. | |
| **Project_Report/** | Contains the final written documentation of the project. | |
| ├── `programming project.docx` | **The Final Report:** Complete written document including Abstract, Methodology, Results, and Conclusions. | (Full Report) |
| ├── **References/** | Initial project proposal, topic selection, and problem definition. | |
| **Datasets/** → **Ground_Truth_Maps/** | Contains all data for validation of the project. |
| ├── `Health_Risk_Index.png` and `Health_Risk_Index(WO).jpg` | **Validated Final Map:** Health Risk Index from the Manual/Software workflow. | Figure 4&5 (Report) |
| ├── `Population_Density.png` |  Manual Population Density Input. | Figure 1 (Report) |
| ├── `Roads_density.png` | Intermediate Output: Road Density Reclassified Layer. | Figure 3 (Report) |
| ├── `Industrial.png`| Industrial Reclassification Input Layer. | Figure 2 (Report) |
| **Datasets/** → **Outputs/** | Contains all the outputs of the project. |
| ├── `Final_Health_Risk_Index.pdf` | Final Output from the Automated (Python) Script (shows fragmented results). | Figure 8&12 (Report) |
| ├── `Population_Density.pdf` | Comparison Image: Python Population Density Input. | Figure 9 (Report) |
| ├── `Roads.pdf` | Python Roads Input. | Figure 11 (Report) |
| `README.md` | This document, outlining the project goals and structure. | |
