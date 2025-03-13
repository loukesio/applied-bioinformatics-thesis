---

# 🚀 **Applied Bioinformatics Thesis**  

Welcome to the **Applied Bioinformatics Thesis** repository! This project focuses on **differential gene expression analysis** and **machine learning applications** using transcriptomics datasets.

---

## 🎯 **Getting Started**  

### 🐍 **Initialize Python Environment**  

🔹 **Minimum Python Version:** **3.11**  

Setting up the Python environment ensures that all dependencies are installed and managed within an isolated environment.

1️⃣ **Activate the virtual environment:**  
```bash
source venv/bin/activate/
```

2️⃣ **Install required dependencies:**  
This command reads the `requirements.txt` file and installs all necessary Python packages.  
```bash
pip install -r requirements.txt
```

---

### 📦 **Enable Git-LFS (Large File Storage)**  

This repository uses **Git Large File Storage (LFS)** to efficiently handle large datasets.  
Ensure you have **Git LFS** installed before cloning the repository.  

📌 **Installation:**
- 📍 **macOS (Homebrew users):**  
  ```bash
  brew install git-lfs
  ```
- 📍 **Ubuntu/Linux (APT package manager):**  
  ```bash
  sudo apt install git-lfs
  ```
- 📍 **Windows (via Chocolatey):**  
  ```bash
  choco install git-lfs
  ```

🔹 **Initialize Git-LFS (Run Once Per User Account):**  
```bash
git lfs install
```

💡 **Pro Tip:** If you have already cloned the repository without LFS, you can **pull large files manually** using:  
```bash
git lfs pull
```

---

Here's a **polished and more visually engaging version** of your **Data Sources** section, making it more **informative, structured, and visually appealing**:

---

## 📊 **Data Sources**  

This project utilizes data from the **[Autoimmune Diseases Explorer (ADEx)](https://adex.genyo.es/)**, a comprehensive database that integrates **82 curated transcriptomics and methylation studies** covering **5,609 samples** from some of the most common **autoimmune diseases**.

### 🔬 **What is ADEx?**  
ADEx provides an **interactive and easy-to-use platform** for exploring omics datasets, offering:  
✅ **Meta-analysis of autoimmune disease datasets**  
✅ **Differential expression and pathway analysis**  
✅ **Advanced statistical tools for transcriptomics and epigenomics**  

📜 **Reference Paper:** [BMC Bioinformatics, 2021](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-021-04268-4)  
📂 **GitHub Repository:** [GENyO-BioInformatics/ADEx_public](https://github.com/GENyO-BioInformatics/ADEx_public)  

---

### 🏥 **Autoimmune Diseases in This Study**  

| **Acronym** | **Full Term** |
|------------|--------------------------------------|
| **ADs**    | Autoimmune Diseases |
| **SLE**    | Systemic Lupus Erythematosus |
| **RA**     | Rheumatoid Arthritis |
| **SjS**    | Sjögren’s Syndrome |
| **SSc**    | Systemic Sclerosis |
| **SADs**   | Systemic Autoimmune Diseases |
| **T1D**    | Type 1 Diabetes |

Each dataset in ADEx is referenced by its **GEO accession code**, allowing easy retrieval of raw data from the **GEO database**.

---

### 🔍 **Primary Dataset in This Study**  

📌 **Focus Dataset:** **GSE89408**  
- 🧪 **Total Samples:** **180**  
- 👩‍⚕️ **Healthy Controls:** **25**  
- 🦠 **RA Patients:** **152**  
- 🏥 **Tissue Origin:** **Synovial Membrane**  

This dataset provides **valuable insights** into the gene expression patterns in **Rheumatoid Arthritis (RA)** and serves as the foundation for our **differential expression and machine learning analyses**.

---

### 🚀 **Why This Matters?**  
By integrating **curated transcriptomics and epigenomics datasets** with advanced computational tools, we aim to:  
🔹 **Identify key biomarkers** for autoimmune diseases  
🔹 **Enhance classification models** for disease prediction  
🔹 **Uncover potential therapeutic targets**  

---


Here's a **refined, visually structured, and engaging** version of your **Project Structure and Preliminary Results** section:

---

## 📂 **Project Structure**  

This repository is organized into well-defined directories to facilitate **differential gene expression analysis**, **machine learning experiments**, and **biological insights**.

```
applied-bioinformatics-thesis/
├── .github/                      # GitHub-related configurations
├── R/                            # R scripts for differential expression analysis
│   ├── differential_expression_libs.R
│   ├── packages.R
│   ├── run_differential_expression.R
├── adex/                         # Python package for data processing and modeling
│   ├── __init__.py
│   ├── helpers.py
│   ├── mds.py
│   ├── models.py
│   ├── pca.py
│   ├── type_aliases.py
├── data/                         # Raw and processed data storage
│   ├── adex-database/
│   │   ├── **datasets_info.csv**  ⬅️ *(Metadata for datasets)*
│   │   ├── **metadata.csv**  ⬅️ *(Raw count data metadata)*
│   │   ├── samples/
│   │   │   ├── RA/
│   │   │   ├── SLE/
│   │   │   ├── SSc/
│   │   │   ├── SjS/
│   │   │   ├── T1D/
│   │   │   └── archived_not_used/
│   ├── ml/                        # Machine Learning datasets
│   │   ├── **GSE89408_test_set_samples.csv**  ⬅️ *(ML dataset - test set)*
│   │   ├── **GSE89408_top_de_train_genes.csv**  ⬅️ *(Top DE genes for ML)*
│   │   ├── **GSE89408_train_set_samples.csv**  ⬅️ *(ML dataset - training set)*
├── data_csv/                      # Processed datasets in CSV and Parquet format
│   ├── adex-database/
│   │   ├── datasets_info.csv
│   │   ├── metadata.csv
│   │   ├── samples/
│   │   │   ├── RA/
│   │   │   │   ├── **GSE38351_RA_GPL570.tsv.parquet**  ⬅️ *(Processed expression data)*
│   │   │   ├── SLE/
│   │   │   │   ├── **GSE10325_B_cells.tsv.parquet**  ⬅️ *(SLE raw data)*
│   │   │   ├── SSc/
│   │   │   │   ├── **GSE95065.tsv.parquet**
├── notebooks/                     # Jupyter notebooks for data analysis and ML
│   ├── **10_ML_with_top_10_de_genes_as_features.ipynb**  ⬅️ *(ML with top DE genes)*
│   ├── **14_Visualizations.ipynb**  ⬅️ *(Plots & data insights)*
│   ├── **1_Prepare_Parquet_Files.ipynb**  ⬅️ *(Data processing)*
├── requirements.txt                # Python dependencies
├── results/                        # Results of differential expression analysis
│   ├── GSE89408_only_train_samples/
│   │   ├── **edgeR_de_genes.csv**  ⬅️ *(Significant differentially expressed genes)*
│   │   ├── **edgeR_results.csv**  ⬅️ *(Full DE analysis results)*
│   │   ├── **edgeR_smear_plot.png**  ⬅️ *(Visualization of DEGs)*
│   ├── RA_GSE89408/
│   │   ├── edgeR_de_genes.csv
│   │   ├── edgeR_results.csv
│   ├── SLE_RNA_SEQ_WHOLE_BLOOD/
│   │   ├── edgeR_de_genes.csv
│   │   ├── edgeR_results.csv
│   ├── SSc_RNA_SEQ_PERIPHERAL_BLOOD/
│   │   ├── edgeR_de_genes.csv
│   │   ├── edgeR_results.csv
│   ├── SSc_RNA_SEQ_WHOLE_BLOOD/
│   │   ├── edgeR_de_genes.csv
│   │   ├── edgeR_results.csv
├── **README.md**  ⬅️ *(Project documentation)*
├── LICENSE        # Open-source license
```

---

## 📈 **Preliminary Results: Insights from GSE89408**  

Our initial analysis of **GSE89408**, which consists of **180 samples (152 RA, 25 Healthy Controls, Synovial Membrane Tissue)**, has already provided key biological insights:

🔹 **Differential Gene Expression**  
   - Identification of **key upregulated and downregulated genes** in **RA vs. Healthy controls**  
   - edgeR analysis highlights potential **biomarker candidates**  

🔹 **Pathway Analysis**  
   - Enrichment of **immune response pathways**  
   - Activation of **inflammatory cascades** in **RA samples**  

🔹 **Signal Transduction Insights**  
   - Key transcription factors show **differential regulation**  
   - Potential impact on **cell signaling networks**  

🔹 **Causal Pathways**  
   - Identification of **gene regulatory interactions** that may contribute to **RA pathology**  
   - Pathway crosstalk between **T-cell activation, cytokine response, and autoimmunity**  

🚀 **Next Steps:**  
🔬 Further **functional analysis** on the top DE genes  
🧠 Integration with **machine learning models** for classification  
📊 Validation with **additional transcriptomics datasets**  

---
