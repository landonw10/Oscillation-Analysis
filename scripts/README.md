# Scripts

This folder contains R and Python scripts implementing key steps of the analysis pipeline:

### snRNA_seq_analysis.R
Processes single-nucleus RNA-seq data, performs QC, clustering, cell type identification, and marker gene analysis focusing on neuronal subtypes linked to oscillations.

### visium_analysis.py
Loads and preprocesses Visium spatial transcriptomics data, identifies spatial clusters, calculates marker scores for theta and gamma oscillations, and visualizes spatial expression patterns.

### data_integration_analysis.R
Integrates snRNA-seq and Visium data using RCTD spatial deconvolution to infer cell type proportions in spatial spots, visualizing pyramidal and interneuron distributions associated with oscillations.

------------------------------------

### Notes
Scripts correspond to the notebook workflows. For detailed exploration and stepwise analysis with commentary, refer to the notebooks.

The scripts are designed for reproducibility and streamlined execution. Comments within the scripts highlight parameters and sections where users can customize or create necessary adjustments.
