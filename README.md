# Photoluminescence-PL-Data-Preprocessing-and-Deconvolution (2022-2024)

## Overview
This repository provides a comprehensive pipeline for preprocessing and analyzing **photoluminescence (PL) spectra** data, derived from experiments using nanobiosensors for different analyte detection. The data comes from a custom-built optical setup, and this repository includes scripts for preprocessing, deconvolution, and visualization of the PL spectra, enabling detailed analysis of single-walled carbon nanotube (SWCNT) chirality.

### Purpose
The main objective of this repository is to preprocess PL spectrum data to remove background noise, smooth the data, and deconvolute overlapping spectral peaks. This pipeline can be applied to datasets for a variety of analytes detected by nanobiosensors.

Key features of this repository include:
- Loading and processing multiple CSV files with PL spectrum data.
- Background correction, noise removal, and data smoothing using the **Savitzky-Golay filter**.
- Lorentzian peak deconvolution for resolving overlapping spectral peaks.
- Visualization of the processed PL data and spectral features for further analysis.

---

## Technologies and Tools Used
- **Python**: The primary programming language used for data preprocessing, deconvolution, and visualization.
- **NumPy & Pandas**: For handling data matrices and manipulating CSV files.
- **Matplotlib**: For generating plots of PL intensity, individual peaks, and fitted spectra.
- **SciPy**: Used for nonlinear least-squares optimization in the Lorentzian peak deconvolution process.
- **Jupyter Notebooks**: For interactive data analysis and visualization.

---

## Key Project Highlights

### 1. Photoluminescence (PL) Spectrum Analysis
The PL data was captured using a custom-built optical setup:
- **Excitation wavelengths**: 660 nm for the (7,5) and (7,6) chiralities, and 730 nm for the (10,2), (9,4), (8,6), and (8,7) chiralities.
- **Emission range**: 900 to 1400 nm, captured using an IsoPlane SCT-320 spectrometer with a NIRvana 640 ST InGaAs camera.

The Python code processes PL spectrum data by:
- Loading multiple CSV files into a matrix.
- Applying background correction to remove noise.
- Smoothing the data with a **Savitzky-Golay filter**.
- Dividing the data based on excitation wavelength (660 nm and 730 nm).
- Saving the processed datasets and generating visual plots of PL intensity.
- Optionally calculating the **area under the curve (AUC)** for quantitative analysis of intensity variations.

### 2. Deconvolution of Photoluminescence Spectra
The **Lorentzian peak deconvolution** is applied to resolve overlapping spectral features:
- Peak fitting is performed using Lorentzian functions for the (7,5) and (7,6) chiralities at 660 nm, and (10,2), (9,4), (8,6), and (8,7) chiralities at 730 nm.
- The script uses **nonlinear least-squares optimization** to iteratively adjust peak parameters (FWHM, peak center, and intensity) to achieve the best fit.

The deconvolution script produces:
- Fitted peak parameters for each spectrum.
- Visual plots showing individual fitted peaks, combined spectra, and residuals to assess the fit quality.
- Export of fitted parameters in CSV format for further analysis.

---

## Repository Structure
The repository is organized as follows:

1. **/data**:
   - Contains raw and preprocessed PL spectrum data. You will find datasets corresponding to different excitation wavelengths (660 nm and 730 nm) and nanobiosensor experiments for glucose, OPG, and NO detection.
   
2. **/scripts**:
   - Python scripts for preprocessing the PL data, performing deconvolution, and visualizing the results. These scripts include background correction, data smoothing, and Lorentzian peak fitting.

3. **/notebooks**:
   - Jupyter Notebooks for interactive data visualization and analysis of the PL spectra. These notebooks allow users to load the data, run the preprocessing pipeline, and visualize the results step by step.

4. **/results**:
   - Contains processed data, plots, graphs, and results from the deconvolution and preprocessing stages. The visualizations include PL intensity plots, fitted spectra, and analysis of intensity variations.

5. **README.md**:
   - This file provides an overview of the project, instructions on how to use the pipeline, and a summary of the key findings.

---

## How to Use the Preprocessing Pipeline

### 1. Data Preparation
- Ensure that your PL spectrum data is in CSV format and organized as described in the `/data` directory.
- Raw data can be uploaded into the pipeline for background correction and smoothing.

### 2. Running the Preprocessing Script
- Use the Python scripts located in the `/scripts` directory to preprocess the PL spectrum data. Run the main script to load the data, apply background correction, and perform deconvolution.
- The script also allows for filtering data based on excitation wavelength and saving the processed results in CSV format.

### 3. Visualization and Analysis
- Open the Jupyter Notebooks in the `/notebooks` directory for an interactive walkthrough of the data preprocessing steps.
- The notebooks provide a step-by-step guide for loading the data, visualizing the PL spectra, and applying deconvolution.

### 4. Saving the Results
- Processed data, plots, and results are saved in the `/results` directory. These include fitted parameters, visual plots of the spectra, and quantitative analysis results such as AUC calculations.

---
