# 🛠️ Lithology-Aware Drilling Optimization: Utah FORGE Well 56-32

## 📌 Project Overview

This project explores high-frequency drilling data from Utah FORGE Well 56-32 to identify optimal **ROP/WOB ratios** for minimizing **Mechanical Specific Energy (MSE)** across different lithologies. The objective is to build a transferable methodology that supports optimization in future wells drilled from the same pad or geological setting.

## 🎯 Objective

- Cluster the well into **geologically meaningful lithology zones**
- Analyze how **WOB, ROP, RPM**, and **MSE** interact within each zone
- Identify **optimal drilling parameter windows** that correlate with **efficient energy transfer (low MSE)**
- Enable **data-driven optimization strategies** for future wells

## 🧩 Dataset

- **Drilling Data**: High-frequency time-series data (~1M+ rows, 46 columns)
- **Wireline Logs**: Interpolated onto drilling depth (Gamma Ray, DTCO, TNPH)
- **Mud Log**: Manual lithology tops used for macro-zones
- **Fracture Data**: Available as supplementary information (CSV)
- **XRD Data**: Mineralogy samples used for cluster calibration

## 🧠 Methodology

### 1. Data Preparation
- Cleaned and interpolated log data (`GR_TMG`, `DTCO`, `TNPH`)
- Removed outliers in MSE using log transformation and thresholding
- Calculated new performance features (`ROP/WOB ratio`)

### 2. Lithology Zone Identification
Two approaches explored:
- **Manual Lithology Zoning** from Mud Logs:
  - Alluvium (0–3050 ft)
  - Transition Zone (3050–4370 ft)
  - Granodiorite (4370–8800 ft)

- **Unsupervised Clustering (KMeans)**:
  - Applied on standardized log features
  - Tested multiple `k` values using silhouette and Calinski-Harabasz scores
  - Final model used `k=3` on full dataset and was saved via pickle

### 3. Optimization Analysis
- Cluster-wise and zone-wise analysis of:
  - `MSE` vs. `ROP/WOB`, `WOB`, `RPM`
  - Drilling efficiency windows by lithology
- Visualizations:
  - Depth-track cluster profiles
  - Heatmaps and scatter plots by lithology

## 🧰 Tools & Technologies

- **Language**: Python 3.x
- **Libraries**: pandas, numpy, matplotlib, seaborn, scikit-learn
- **Data Format**: CSV, LAS, Parquet
- **Notebook Structure**:
  - `Drilling Data EDA.ipynb`
  - `Lithology Clustering & MSE Analysis.ipynb`

## 📈 Key Findings

- MSE optimization is strongly dependent on lithology zone
- Alluvium required lower WOB and higher RPM for optimal efficiency
- Granodiorite zones showed higher MSE sensitivity to RPM than ROP
- KMeans clustering generally aligned well with known lithology zones

## 🚀 Future Work

- Validate results on upcoming Utah FORGE wells
- Apply clustering + MSE optimization framework to other geothermal or hard-rock wells
- Incorporate downhole vibrations and BHA metadata into efficiency modeling

## 📁 Repository Structure

