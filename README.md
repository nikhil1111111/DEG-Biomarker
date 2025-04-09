# 🧬 Multi-Cancer Gene Expression Analysis for Biomarker Discovery and Classification

This project performs a comprehensive analysis of gene expression profiles across multiple cancer types. It involves differential gene expression analysis, dimensionality reduction, hierarchical clustering, machine learning classification, and gene-gene co-expression network visualization.

## 📁 Dataset

- The dataset used is a `.rds` file containing gene expression values for **9,263 samples** across **24 cancer types**, with expression levels for **716 genes**.
- Each sample includes metadata such as:
  - `Sample` — Unique sample identifier
  - `Cancertype` — Type of cancer (e.g., BRCA, LUAD, GBM)
  - Gene expression values as numerical features

## 🧪 Analyses Performed

### 1. **Exploratory Data Analysis**
- Dataset summary and structure inspection
- Count of samples per cancer type
- Mean and standard deviation of gene expression levels
- Identification of top 5 most variable genes

### 2. **Differential Gene Expression (DGE) Analysis**
- Performed a **t-test** between selected cancer types (e.g., BRCA vs LUAD)
- Identified top 10 differentially expressed genes based on p-values
- Visualized with a heatmap

### 3. **Unsupervised Learning**
- **Hierarchical Clustering** using Ward’s method
- **t-SNE** for nonlinear dimensionality reduction
- **PCA** for principal component visualization

### 4. **Supervised Classification**
- Trained a **Random Forest Classifier** to predict cancer type from gene expression profiles
- Evaluated using:
  - Accuracy: `92.17%`
  - Precision, Recall, F1-Score
- Extracted top predictive genes based on feature importance

### 5. **Gene-Gene Co-expression Network**
- Calculated correlation matrix for the top 100 variable genes
- Visualized co-expression relationships using a heatmap

## 📊 Key Results

- **Top 10 Differentially Expressed Genes** between BRCA and LUAD:
  - `PITPNM1`, `PPP4R1`, `MVP`, `AR`, `SUPT7L`, etc.
- **Top Predictive Genes** (from Random Forest):
  - `ESR1`, `TP63`, `PPARG`, `AR`, `CDK2`, etc.
- **Highest Variability Genes**:
  - `UBB`, `HIST1H1C`, `UBC`, `PFN1`, `DAXX`

## 🔧 Tools & Libraries Used

- **Python Libraries**: `pandas`, `numpy`, `pyreadr`, `matplotlib`, `seaborn`, `scipy`, `sklearn`
- **Statistical Tests**: t-test (scipy)
- **ML Models**: Random Forest Classifier
- **Dimensionality Reduction**: PCA, t-SNE
- **Visualization**: Heatmaps, Scatter plots, Dendrograms

## 📌 How to Run

1. Open the notebook in **Google Colab**
2. Upload the `.rds` dataset file
3. Install dependencies if needed:
   ```bash
   pip install pyreadr seaborn scikit-learn
