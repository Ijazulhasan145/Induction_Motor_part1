# Induction_Motor_part1

# Motor Fault Diagnosis using k-NN and PCA

This project implements a machine learning pipeline for **motor fault diagnosis** using **k-Nearest Neighbors (k-NN)** and **Principal Component Analysis (PCA)**. The goal is to classify different motor health conditions based on **Current-A signal data** collected from three-phase induction motors.

## Objective

Diagnose and classify **14 different motor conditions**, including:

* Inner/outer race bearing faults (0.7mm to 1.7mm severity)
* Broken rotor bars
* Healthy motor states
  ... using time-series data from induction motors.

---

## Dataset Description

* **Signals:** Instantaneous Current-A values from 3-phase current data.
* **Sampling Rate:** 10 kHz, with 1000 samples per block.
* **Load Conditions:** 100W, 200W, 300W.
* **Total Classes:** 14 (including healthy and faulty motor states)
* **Files:** 39 CSV files, each representing a unique motor condition.

---

## echniques Used

### k-Nearest Neighbors (k-NN)

* Implemented **from scratch** without using ML libraries.
* **Custom Euclidean Distance Function**.
* **k = 2** chosen as optimal after testing values from 1 to 14.
* Evaluated using:

  * **Hold-Out Validation (80/20)**
  * **10-Fold Cross-Validation**
  * Metrics: Accuracy, Precision, Recall, F1-score, Confusion Matrix

### Principal Component Analysis (PCA)

* **Min-Max normalization** applied to all features.
* Dimensionality reduced while retaining **95% variance**.
* Reapplied k-NN on PCA-transformed data.

---

## Results

| Metric           | Without PCA    | With PCA              |
| ---------------- | -------------- | --------------------- |
| Accuracy         | 27.14%         | 68%                   |
| Micro F1-Score   | 27%            | \~68%                 |
| Macro F1-Score   | 29%            | Improved              |
| Confusion Matrix | High Confusion | Improved Separability |

* **PCA helped reduce noise** and improve class separation.
* Significant improvement in performance by reducing dimensionality.

---

## Future Improvements

* Explore advanced algorithms like **SVM** or **Random Forest**.
* Use **feature extraction techniques** like FFT or Wavelet Transform.
* Try **Deep Learning** methods for automatic feature learning.

---

## Technologies Used

* Python
* NumPy, Pandas
* Matplotlib, Scikit-learn (only for PCA)
* Jupyter Notebook


