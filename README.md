# Multimodal Presurgical Brain Tumor Classification
**STAT3612 Group Project 

This repository contains our team's systematic approach to classifying brain tumors using multimodal data (Imaging, Clinical, and Text). Our goal is to evaluate the contribution of each modality and build a robust, integrated classifier.

---

## 📊 Phase 1: Clinical Data & Feature Engineering
We explore the demographic and radiomics data to prepare them for the algorithms.

*   **Categorical Encoding:** We plan to convert text labels (e.g., Gender) into numerical values (1s and 0s) so the models can process them mathematically.
*   **Age Binning:** We can group exact ages into broader categories (e.g., Young Adult, Senior) to reduce noise and focus on medical life stages.
*   **Feature Interaction:** We aim to create combined features, such as `Age × Gender`, to help the model identify patterns that only exist in specific demographics (e.g., specific tumors more common in older females).
*   **Statistical Summaries (Radiomics):** For continuous data, we can use the **Mean** (average brightness), **Standard Deviation** (texture roughness), and **Skewness** (outlier spots) as simplified inputs.

---

## 🧠 Phase 2: Modality-Specific Models (Level 0)
We plan to tune individual models for each data type before combining them.

*   **Tabular Models (LGBM & XGBoost):** We focus on **LightGBM (LGBM)** for its speed during initial tuning. We can also compare results with **XGBoost**, **SVM**, and **Random Forest**.
*   **Image Features (PCA + SVM):** For the 8,192 ResNet features, we aim to use **Principal Component Analysis (PCA)** to compress the data. This allows us to use SVM or Boosting models more efficiently. 
  Neural networks are worth trying but they does not guarantee optimal results.
  
    **Text Analysis (NLP):** We can explore using a Transformer (like BERT) to extract meaningful insights from the radiology reports.

---

## 🥞 Phase 3: Integration Strategy (Stacking)
The final phase involves exploring how to best combine our individual models.

*   **Model Stacking:** Instead of joining the raw data, we can take the *predictions* (probabilities) from our Phase 2 models and feed them into a final "Meta-Classifier."
*   **Voting System:** We can also test if a simpler voting system (averaging the predictions) achieves similar or better results than a complex stack.
