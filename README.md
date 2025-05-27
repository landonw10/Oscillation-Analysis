# Oscillation-Analysis
Integrated single-nucleus RNA-seq and spatial transcriptomics to map cellular and molecular organization of theta and gamma oscillation networks in hippocampal and cortical circuits during spatial object recognition. Identified distinct neuronal subtypes driving oscillatory patterns and their spatial distribution.

## Repository Overview
### notebooks -> created
R-markdown and Jupyter notebooks of pipelines with detailed descriptions of workflow
### reports -> in progress
HTML of full pipeline including outputs using example data
### scripts -> in progress
Each individual script used in the pipelines

## Three complementary analysis pipelines:
### 1. Single-Nucleus RNA-seq Analysis (snRNA_analysis.Rmd)
Purpose: Identifies cell types and clusters associated with theta and gamma oscillation markers

Key Packages: Seurat, Matrix, dplyr, ggplot2

Key Steps:

Data Loading & QC: Loads count matrix, gene annotations, and cell metadata

Pre-filtering: Removes multiplets (RNA count < 35,000) and low-quality cells (mitochondrial % < 10%)

Normalization & Scaling: Standard Seurat normalization, variable feature detection, and data scaling

Dimensionality Reduction: PCA and UMAP for visualization and clustering

Clustering: Graph-based clustering to identify distinct cell populations

Differential Expression: Wilcoxon rank-sum tests with FDR correction to identify clusters with significant theta (Hcn1) and gamma (Pvalb) marker expression

Cell Type Annotation: Uses canonical CNS markers to classify neuronal subtypes (glutamatergic, GABAergic, astrocytes)

### 2. Spatial Transcriptomics Analysis (Visium_analysis.ipynb)

Purpose: Maps spatial distribution of oscillation markers across tissue architecture

Key Packages: scanpy, numpy, matplotlib, pandas, scipy

Key Steps:

Data Loading: Imports 10x Visium spatial transcriptomics data

Quality Control: Filters low-quality spots (min 200 counts) and rarely expressed genes (min 3 cells)

Normalization: Total count normalization (10,000 counts per spot) followed by log1p transformation

Feature Selection: Identifies highly variable genes for downstream analysis

Spatial Clustering: Leiden clustering to identify spatially coherent brain subregions

Marker Analysis: Single and multi-marker approaches to quantify theta/gamma expression patterns

Outlier Detection: Identifies and removes spots with extreme expression values

Spatial Visualization: Maps gene expression and marker scores onto tissue coordinates

### 3. Data Integration & Deconvolution (Data_integration_analysis.Rmd)

Purpose: Integrates single-cell reference with spatial data to estimate cell type compositions and validate oscillation-cell type relationships

Key Packages: Seurat, spacexr, Matrix, ggplot2, dplyr, patchwork

Key Steps:

Reference Preparation: Uses single-nucleus data to create cell type reference profiles

Spatial Deconvolution: RCTD (Robust Cell Type Decomposition) to estimate cell type proportions in spatial spots

Cell Type Mapping: Projects pyramidal neuron and interneuron proportions onto spatial coordinates

Cross-Modal Validation: Correlates deconvolved cell type proportions with spatial gene expression

Statistical Testing: Spearman correlations to test associations between Pyramidal cell proportions and theta markers (Hcn1) Interneuron proportions and gamma markers (Pvalb)

## Key Findings

Theta Networks: Enriched in pyramidal neuron populations expressing Hcn1

Gamma Networks: Concentrated in parvalbumin-positive interneuron clusters

Spatial Organization: Distinct anatomical localization of oscillation-associated cell types

Cross-Modal Validation: Consistent theta/gamma signatures across single-cell and spatial modalities
