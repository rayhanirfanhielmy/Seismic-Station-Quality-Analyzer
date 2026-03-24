# Seismic Station Quality Analyzer 🌍📊

An automated Python pipeline designed to evaluate the site quality and ambient noise characteristics of any broadband seismic station worldwide. This tool combines standard seismological signal processing with unsupervised machine learning to provide a comprehensive and objective site evaluation.

## 🚀 Features
1. **Memory-Optimized Data Acquisition:** Automatically downloads continuous waveform data via FDSN (e.g., GFZ, IRIS) and saves progress day-by-day to prevent RAM overload during long-term analysis.
2. **Ambient Noise Analysis (PSD & RMS):** Computes Power Spectral Density (PSD) using Welch's method and extracts Root Mean Square (RMS) acceleration in the anthropogenic frequency band (e.g., 1-10 Hz).
3. **Machine Learning Clustering:** Utilizes Fuzzy C-Means (FCM) clustering to objectively classify diurnal and weekly seismic noise patterns without human bias.
4. **Local Site Effect (HVSR):** Computes the Horizontal-to-Vertical Spectral Ratio (HVSR) based on the international SESAME guidelines using raw counts and Konno-Ohmachi smoothing to determine the fundamental resonance frequency (f0) and amplification factor.

## 🛠️ Requirements
This script is fully optimized for **Google Colab** and Jupyter Notebook environments.
Dependencies used:
* `obspy`
* `scipy`
* `numpy`
* `pandas`
* `scikit-fuzzy`
* `cartopy`
* `seaborn`
* `matplotlib`

## ⚙️ How to Use
You can evaluate any seismic station worldwide by modifying the configuration block in **Cell 2** and **Cell 11** of the notebook:

```python
client = Client("GFZ")       # Network provider (e.g., IRIS, GFZ)
network = "GE"               # Network code (e.g., GE, IU, II)
station = "UGM"              # Your target station code
location = "*"               
channel = "SH?"              # Sensor channel (e.g., BH?, SH?, HH?)
```

## 📈 Outputs Generated
Running the notebook will generate publication-ready, high-resolution figures, including:
* **Figure 1:** Regional Map with geographic coordinates and station layout.
* **Figure 2-6:** Diurnal polar plots, hourly boxplots, median lineplots, and spectrograms.
* **Figure 7:** FCM Cluster distribution validating anthropogenic noise sources.
* **Figure 8:** Standardized HVSR Curve with geometric mean and standard deviation boundaries.

## 📝 License
This project is open-source and available under the **MIT License**. You are free to use, modify, and distribute this software, provided that proper credit is given to the original author.
