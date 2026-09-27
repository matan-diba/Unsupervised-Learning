# Clinical Patient Phenotyping & Risk Stratification via Unsupervised Learning

An unsupervised machine learning pipeline for diabetic patient phenotyping and 30-day readmission risk stratification using multi-dimensional Electronic Health Records (EHR).

## 📌 Project Overview
In chronic disease management, one-size-fits-all clinical protocols often fail due to high patient heterogeneity. Utilizing clinical and demographic data from hospital admissions (based on the UCI Diabetes 130-US Hospitals dataset), this project discovers latent clinical sub-types (phenotypes) to identify high-risk clusters, reduce avoidable 30-day hospital readmissions, and enable personalized care pathways.

## 🔬 Pipeline Architecture
1. **Data Preprocessing & Robust Imputation:**
   * Handled missing medical values via median (numerical) and most-frequent (categorical) strategies.
   * Robust scaling (`RobustScaler`) to mitigate the influence of severe hospital stay and medication outliers.
   * Categorical feature transformation using `OneHotEncoder`.
2. **Dimensionality Reduction:**
   * **PCA:** Quantified linear variance distribution and captured principal clinical axes.
   * **UMAP:** Non-linear topological manifold learning preserving local and global geometric relationships.
3. **Clustering & Phenotyping Algorithms:**
   * **K-Means:** Baseline distance-based partitioning.
   * **Gaussian Mixture Models (GMM):** Probabilistic soft-clustering reflecting multi-faceted clinical phenotypes.
   * **Agglomerative Hierarchical Clustering (HAC):** Dendrogram analysis of hierarchical patient relationships.
   * **DBSCAN:** Density-based grouping and clinical anomaly/outlier detection.

## 📊 Evaluation & Clinical KPIs
* **Internal Mathematical Metrics:** Evaluated cluster quality via Silhouette Score, Davies-Bouldin Index (DBI), and Calinski-Harabasz Index.
* **Clinical Correlation:** Mapped mathematical clusters to real-world healthcare KPIs:
  * 30-day readmission incidence.
  * Average Length of Stay (LOS).
  * Medication and comorbidity complexity index.
* **Key Finding:** Higher lab test frequencies and prior inpatient admissions strongly correlated with higher readmission clusters, demonstrating that mathematical clustering successfully captured genuine clinical acuity.

## 🛠 Tech Stack
* **Language:** Python
* **Libraries:** scikit-learn, UMAP-learn, Pandas, NumPy, SciPy, Seaborn, Matplotlib
