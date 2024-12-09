# Analysis of O-GlcNAcylation Dysregulation in Cancer

This repository contains Jupyter notebooks to investigate the impact of O-GlcNAcylation dysregulation on cancer through data-driven methodologies. The analysis uses gene expression data from TCGA (The Cancer Genome Atlas) to quantify dysregulation.

---

## Files in This Repository

1. **`1_data_download.ipynb`**  
   This notebook provides step-by-step instructions to download RNA-seq gene expression data from the GDC portal using the GDC Data Transfer Tool. It specifies how to structure and organize downloaded files for further analysis.

2. **`2_KDE_generation.ipynb`**  
   This notebook generates Kernel Density Estimates (KDEs) for visualizing and analyzing OGT and OGA expression distributions across different cancer types.

3. **`3_simulation_runs.ipynb`**  
   This notebook simulates data to compare different metrics, including KDE-based measures and other regulation measures, for distinguishing between healthy and cancerous tissues.

4. **`4_modeling.ipynb`**  
   This notebook performs modeling using real cancer datasets, quantifying the relationship between OGT and OGA expression. It provides statistical insights into O-GlcNAcylation dysregulation across cancers.

---

## Prerequisites

- Python 3.8 or later
- Jupyter Notebook
- Required Python libraries: numpy, pandas, matplotlib, seaborn, scipy, sklearn (refer to each notebook for specific imports)

---

## Data Requirements and Organization

### TCGA Gene Expression Data
For the analysis, RNA-seq gene expression data must be downloaded and organized as follows:

1. Go to the [GDC Portal](https://portal.gdc.cancer.gov/).
2. Select the cancer type of interest by tissue (e.g., Breast, Blood and Bone Marrow, etc).
3. Under the **Repository**, apply the following filters:
   - **Experimental Strategy**: RNA-seq
   - **Data Category**: Transcriptome Profiling
   - **Data Type**: Gene Expression Quantification
4. Use the **GDC Data Transfer Tool** to download the sample gene expression data.
5. Organize the downloaded `.tsv` files in the following structure:

   ```
   /data/TCGA_GeneExpression/{cancer}/gene_expression/
   ```
   Replace `{cancer}` with the specific cancer type.

### Example Directory Structure

```
data/
└── TCGA_GeneExpression/
    ├── Kidney/
    │   └── gene_expression/
    │       ├── sample_1.tsv
    │       ├── sample_2.tsv
    │       └── ...
    ├── Lung/
    │   └── gene_expression/
    │       ├── sample_1.tsv
    │       ├── sample_2.tsv
    │       └── ...
```

---

## Usage Instructions

1. **Data Download**:  
   Run the `1_data_download.ipynb` notebook to confirm data requirements and download the necessary files.

2. **KDE Generation**:  
   Execute `2_KDE_generation.ipynb` to compute and visualize KDEs for the selected cancer types.

3. **Simulation Runs**:  
   Use `3_simulation_runs.ipynb` to simulate data and compare different measures of regulation.

4. **Modeling**:  
   Run `4_modeling.ipynb` for application of the methodology to TCGA datasets.

---

## Notes

- Ensure the data is preprocessed as described in `1_data_download.ipynb` before proceeding to the analysis notebooks.
- Modify paths and cancer types in each notebook as necessary.

---
