# Species Distribution Modeling: Invasive Species on Fogo Island

## 🌿 Project Overview
This project focuses on forecasting the potential distribution of the most frequently introduced plant species on Fogo Island (Cabo Verde). 
Developed during the GeoTraining Summer School 2024 (Frankfurt), the study integrates bioclimatic data with satellite-derived land cover to identify environmental niches and invasion hotspots.

## 🛠️ Technical Workflow & Methodology
The study employs a rigorous statistical modeling framework (GLM) implemented through a reproducible R pipeline:

1. **Environmental Data Acquisition**:

  * Bioclimatic Variables: Dynamically retrieved from the WorldClim database via the geodata API.

  * Land Cover Integration: Utilized a custom land cover layer (prepared via Sentinel-2 classification) to add local-scale ecological constraints.

2. **Spatial Preprocessing**:

  * Alignment: Systematic cropping, masking, and resampling of all environmental layers to a common spatial resolution and extent using the terra package.

3. **Modeling Framework (GLM)**:

  * Sampling Strategy: Generation of pseudo-absence points to complement opportunistic occurrence data.

  * Validation: Splitting data into Training (80%) and Test (20%) sets to ensure model generalizability.

  * Algorithms: Generalized Linear Models (GLM) utilized to estimate the probability of occurrence based on environmental predictors.

4. **Evaluation & Mapping**:

  * Performance: Thresholding of probability maps to produce binary "suitability" maps.

  * Metrics: Rigorous evaluation using Confusion Matrices, AUC, and Kappa statistics.

  * Prediction: Generation of high-resolution suitability maps for the entire island.

## 🧰 Tech Stack

* Language: R

* Spatial Libraries: terra, sf, geodata

* Modeling Engine: predicts, stats

* Workflow: Modular R scripting for end-to-end reproducibility.

## 📊 Key Results

![Figure 1: Map of the species presence probability.](outputs/Fig1_probability_map.png)

The model successfully identified temperature seasonality, precipitation and land cover as primary drivers of the species' expansion.
The northern and central regions of Fogo were found to be the most suitable, covering both vegetation and settlement areas. 
Conversely, unsuitable areas were identified in the rocky landscape.

## 👥 Team & Credits

* Developed as a collaborative project during the GeoTraining 2024.

* Team Lead: SODE A. Idelphonse
Collaborators: Olajide A.Y., Nakhwala L., Opara A., Opoku M., Barasa C.W.