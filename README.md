# Identifying cell-cell interactions that lead to metastatic PDAC progression

This repo contains codes to generate the analysis results (figures, tables) for 20.440 class project.

Motivation for this project: with the success of immune checkpoint inhibitors in the clinic, more and more attention has been drawn to the question of how tumor microenvironment (TME) influences tumor progression. The interactions between immune cells and cancer cells determine whether the tumor is eliminated, metastasizes, or is maintained in a dormant state. Recent studies have used bulk genomic and transcriptomic analysis to uncover that the TME consists of tumor-promoting and tumor-suppressive signals that affect tumor progression. However, bulk analysis does not provide the resolution to decipher which specific TME cell subpopulations are interacting with each other, providing and receiving these signals. Therefore, for this project, we plan to use scRNA-seq data to identify the significant cell-cell interactions that lead to tumor progression.

Most of the scRNAseq analysis will be based on standard [Seurat](https://satijalab.org/seurat/) Processing and [Connectome](https://msraredon.github.io/Connectome/)

# Data

Data is downloaded from "Transcriptional subtype-specific microenvironmental crosstalk and tumor cell plasticity in metastatic pancreatic cancer", Raghavan, S., Winter, P. S., Navia, A. W.,  BioRxiv, 2020.08.25  

# Folder Structure

### data
All data-related files are in `data/` folder:

* `tumorANDimmune/` contains raw counts and meta data for both tumor and immune cells
* `immune_only/` contains raw counts and meta data for only immune populations, with additional information of corresponding tumor severity

### source code
All of the code is in the `src/` folder

### output
All analysis output (raw tables, clean tables, figures) will be in the `output/` folder

### visualization
The final  figures are in the `visualization/` folder

# Installation

To reproduce the analysis in this repo, you will need to install the following packages: dplyr, Seurat, patchwork, ggplot2, Connectome, Rstudio(optional)

# Pseudocode to generate the first figure (pset4)

Pseudocode:
1. extract data and metadata from the csv files
2. create Seurat object for the counts of each cell
3. normalize the data
4. identify the 10 most variable genes
5. plot the variable features w/ labels
6. perform PCA dimensional reduction
7. visualize PCA clusters
7. find clusters with UMAP and tSNE using only significant PCs
8. plot clusters
