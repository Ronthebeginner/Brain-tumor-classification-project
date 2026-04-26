# SDST3612: Multimodal Brain Tumor Classification

This project tackles the complex presurgical classification of five brain tumor subtypes using multimodal data (Imaging, Clinical, and Text). Our goal is to evaluate the contribution of each modality and build a robust, integrated classifier.

## 🔬 Methodology 
Our pipeline was developed in three major phases:

1. **Independent Unimodal Training & Exploratory data analysis**

   Before fusion, we isolated each data modality. We trained baseline models (Linear SVC, Random Forest, XGBoost) independently on image    features, radiomics, and clinical text to quantify their isolated predictive power and understand their failure modes on rare classes.
   
2. **Feature Optimization & Dimensionality Reduction:** 

   To combat the "curse of dimensionality" and high noise, we applied variance thresholds, collinearity filtering, and PCA. We also utilized a dual-pathway text extraction method (TF-IDF + clinical knowledge-driven rules) to handle unstructured radiology reports.
   
3. **Multimodal Fusion:** 

   We utilized decision-level ensemble methods (Soft Voting and Naive Bayes) to aggregate predictions. This approach allowed models to specialize by modality while dynamically handling patients with missing MRI sequences during inference.

## 👥 Team Workload Distribution
* **Myriam:** Deep image features preliminary analyis, visualisations, model comparison
* **Ronny:** Ablation study on deep image features, visualisations, PCA analysis, model comparison
* **Charles:** Multimodal Ensemble Strategies (Soft Voting, Naive Bayes) and Final Pipeline Integration.
* **Liao & Jun:** Clinical Information and NLP (Textual feature engineering, TF-IDF, Keyword matching)

### 🧪 Experimentation & Ablation Study
My testing is located in the `Ronny` directory.
* [**View Ablation Study Notebook**](./Ronny/ablation_study.ipynb)

### 📄 Project Report
For a detailed analysis of my results, please refer to the:
* [**Brain Tumor Project Report (Section 3.4 - 3.5)**](./brain%20tumor%20project%20report.pdf#page=6)


