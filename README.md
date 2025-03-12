# Applied Bioinformatics Thesis

## Initialize Environment

### Initialize Python Environment 

Minimum Python Version: **3.11**
```
# Activate the virtual environment
# This ensures that all dependencies are installed and managed within an isolated environment.

source venv/bin/activate/

# Install the required dependencies
# This reads the `requirements.txt` file and installs all necessary Python packages listed in it.

pip install -r requirements.txt
```
### Initialize Git-LFS (Large File Storage)

Needs an installation of [git-lfs](https://git-lfs.com). 
(For **macOS** systems if you are using [Brew](https://brew.sh): `brew install git-lfs`)

```bash
git lfs install  # You only need to run this once per user account.
```

### Data Sources

Our Data source is Autoimmune Diseases Explorer (https://adex.genyo.es), a database that integrates 82 curated transcriptomics and methylation studies covering 5609 samples for some of the most common autoimmune diseases. The database provides, in an easy-to-use environment, advanced data analysis and statistical methods for exploring omics datasets, including meta-analysis, differential expression or pathway analysis.


| Acronym | Full Term |
|---------|--------------------------------------|
| ADs     | Autoimmune Diseases |
| SLE     | Systemic Lupus Erythematosus |
| RA      | Rheumatoid Arthritis |
| SjS     | Sjögren’s Syndrome |
| SSc     | Systemic Sclerosis |
| SADs    | Systemic Autoimmune Diseases |
| T1D     | Type 1 Diabetes |

### Project Structure 

```
applied-bioinformatics-thesis/
├── .github/
├── R/
│   ├── differential_expression_libs.R
│   ├── packages.R
│   ├── run_differential_expression.R
├── adex/
│   ├── __init__.py
│   ├── helpers.py
│   ├── mds.py
│   ├── models.py
│   ├── pca.py
│   ├── type_aliases.py
├── data/
│   ├── adex-database/
│   │   ├── datasets_info.csv  ⬅️ **(Metadata for datasets)**
│   │   ├── metadata.csv  ⬅️ **(Raw count data metadata)**
│   │   ├── samples/
│   │   │   ├── RA/
│   │   │   ├── SLE/
│   │   │   ├── SSc/
│   │   │   ├── SjS/
│   │   │   ├── T1D/
│   │   │   └── archived_not_used/
│   ├── ml/
│   │   ├── GSE89408_test_set_samples.csv  ⬅️ **(ML dataset - test set)**
│   │   ├── GSE89408_top_de_train_genes.csv  ⬅️ **(Top DE genes for ML)**
│   │   ├── GSE89408_train_set_samples.csv  ⬅️ **(ML dataset - training set)**
├── data_csv/
│   ├── adex-database/
│   │   ├── datasets_info.csv
│   │   ├── metadata.csv
│   │   ├── samples/
│   │   │   ├── RA/
│   │   │   │   ├── GSE38351_RA_GPL570.tsv.parquet  ⬅️ **(Processed expression data)**
│   │   │   ├── SLE/
│   │   │   │   ├── GSE10325_B_cells.tsv.parquet  ⬅️ **(SLE raw data)**
│   │   │   ├── SSc/
│   │   │   │   ├── GSE95065.tsv.parquet
├── notebooks/
│   ├── 10_ML_with_top_10_de_genes_as_features.ipynb  ⬅️ **(ML with top DE genes)**
│   ├── 14_Visualizations.ipynb  ⬅️ **(Plots & data insights)**
│   ├── 1_Prepare_Parquet_Files.ipynb  ⬅️ **(Data processing)**
├── requirements.txt
├── results/
│   ├── GSE89408_only_train_samples/
│   │   ├── edgeR_de_genes.csv  ⬅️ **(Significant differentially expressed genes)**
│   │   ├── edgeR_results.csv  ⬅️ **(Full DE analysis results)**
│   │   ├── edgeR_smear_plot.png  ⬅️ **(Visualization of DEGs)**
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
├── README.md  ⬅️ **(Project documentation)**
├── LICENSE

```
