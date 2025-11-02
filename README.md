# Indoor Localization and Wi-Fi Fingerprinting

**Course:** DSAI 3201 – Machine Learning
**University:** University of Doha for Science and Technology

---

## Project Overview

This project explores **Indoor Localization using Wi-Fi Fingerprinting** based on the **UJIIndoorLoc Dataset**. It aims to estimate device locations in indoor environments where GPS is unavailable or unreliable (e.g., malls, offices, or underground buildings).

Two main tasks were performed:

1. **Classification:** Predict *Building ID* and *Floor Level* using RSSI (Wi-Fi signal strength) data.
2. **Regression:** Predict *Longitude* and *Latitude* coordinates using machine learning and deep learning models.

---

## Objectives

* Develop and evaluate **classification models** (Decision Tree, SVM, Random Forest) to identify building and floor.
* Implement **regression models** (Neural Network, CNN) for coordinate prediction.
* Compare performance between traditional and deep learning approaches.
* Optimize hyperparameters using **Differential Evolution** for improved model accuracy.

---

## Dataset Information

**Dataset:** [UJIIndoorLoc](https://doi.org/10.24432/C5MS59)

* **520 RSSI Features:** Wi-Fi signal strengths from access points (WAP001–WAP520)
* **Positional Attributes:** Longitude, Latitude, Floor, Building ID
* **Additional Context:** Space ID, Relative Position, User ID, Phone ID, Timestamp

### Data Preprocessing Steps

* Replaced “no signal” values (100) with **–105 dBm**
* Removed undetected WAPs (all-zero columns)
* Scaled numerical features with **MinMaxScaler(0, 1)**
* Optional PCA experiments were tested but not retained for interpretability reasons

---

## Methodology

### 1. **Classification Models**

* **Decision Tree:** Simple, interpretable baseline
* **Support Vector Machine (SVM):** Linear kernel for high-dimensional RSSI data
* **Random Forest:** Ensemble approach, best performer for both Building and Floor

### 2. **Regression Models**

* **Neural Network (NN):** Fully connected layers for coordinate prediction
* **Convolutional Neural Network (CNN):** Captures spatial signal patterns
* **Optimization:** Hyperparameters tuned via **Differential Evolution**

### 3. **Evaluation Metrics**

* **Classification:** Accuracy, Precision, Recall, F1-macro
* **Regression:** RMSE, MAE, R²

---

## Results Summary

| Model          | Task       | Key Metric | Score                               | Notes                     |
| :------------- | :--------- | :--------- | :---------------------------------- | :------------------------ |
| Decision Tree  | Building   | F1-macro   | 0.99                                | High interpretability     |
| Random Forest  | Floor      | F1-macro   | **0.9965**                          | Best classification model |
| Neural Network | Longitude  | RMSE       | 0.0315                              | 12.29 m avg. error        |
| CNN            | Latitude   | RMSE       | 0.0324                              | Comparable to NN          |
| Tuned NN       | Validation | RMSE       | **0.0333 (Lon)** / **0.0433 (Lat)** | Best generalization       |

---

## Tools and Libraries

* **Python**
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `torch`
* **AI Assistance:**

  * *ChatGPT-4o* for syntax debugging, CNN optimization, and differential evolution code
  * *Scribbr Citation Generator* for APA-formatted references

---


## References

1. Torres-Sospedra, J. et al. (2014). *UJIIndoorLoc Dataset.* UCI Machine Learning Repository.
2. Chelly, M., & Samama, N. (2009). *New Techniques for Indoor Positioning.* ENC-GNSS.
3. Cheng, E. (2025). *Location Fingerprinting – What is it, and should you choose it?* Pointr.
4. IBM (2024). *What is PCA?* IBM Think.
5. MetaGeek (n.d.). *Wi-Fi Signal Strength Basics.*

