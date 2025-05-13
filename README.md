# Dynamic MSE Analysis & Lithology Clustering – Utah FORGE Well 56-32

This project applies data science techniques to optimize drilling performance for the Utah FORGE Well 56-32. It focuses on the integration of high-frequency drilling data and wireline logs to analyze **Mechanical Specific Energy (MSE)** trends, identify **lithological zones** through clustering, and support optimization window identification.

---

## 🔍 Project Objective

To explore the relationship between MSE and formation lithology using unsupervised machine learning. The goal is to identify optimal drilling parameter zones and detect efficiency losses due to formation changes or dysfunctions.

---

## 📁 Dataset Sources

- **Drilling Data**: High-frequency (~1 Hz) surface and downhole sensor readings (~2.5M rows).
- **Wireline Log**: Processed LAS file from 3452–9050 ft containing `GR_TMG`, `DTCO_MPS_R`, and `TNPH`.
- **Mineralogy Ground Truth**: Linearized XRD results for 69 core samples.

---

## ✅ Project Milestones

### 1. **Drilling Data Preparation**
- Filtered and prioritized 43 essential columns out of 296.
- Cleaned `Bit Depth` for reliable interpolation.

### 2. **Wireline Log Integration**
- Interpolated key logs (`GR_TMG`, `DTCO`, `TNPH`) onto drilling dataset using bit depth matching.

### 3. **Lithology Clustering**
- Applied **KMeans clustering** on log data to segment subsurface into lithological zones.
- Selected optimal `k = 4` based on:
  - **Elbow Method**
  - **Silhouette Score**

### 4. **Visualization**
- Plotted clusters over depth vs log crossplots to validate geological consistency.
- Depth-color-coded scatter plots to show transitions and validate model insight.

### 5. **XRD Mineralogy Calibration (Optional Step)**
- Preprocessed and linearized XRD dataset.
- Set up for future validation of lithology zones against mineral composition.

---

## 🧠 Methods & Tools

- **Python Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
- **EDA & Interpolation**: Custom interpolation on bit depth, correlation analysis
- **Clustering**: KMeans with visual diagnostic tools
- **Optional Ground Truth**: Linearized XRD + core sample matching

---

## 📊 Key Outputs

- 📈 **Elbow & Silhouette Score Graphs** for cluster evaluation  
- 🌍 **Clustered Lithology Visualization** across depth and logs  
- 📐 **Framework for MSE Optimization Zones**
