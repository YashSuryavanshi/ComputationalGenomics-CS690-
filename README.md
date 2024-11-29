 
---

# Computational Genomics - Clustering and Dimensionality Reduction  

## Overview  
This project is part of the **Computational Genomics (CS690)** course under the guidance of **Prof. Hamim Zafar** at **IIT Kanpur**. It explores advanced computational techniques to analyze single-cell RNA-sequencing and imaging-based spatial transcriptomics datasets.  

The project involves:  
- **Single-cell RNA-seq data clustering** using Leiden and deviance-based methods.  
- **Variational Autoencoder (VAE)** and **SCVI-based latent space models** for dimensionality reduction.  
- Clustering of **MERFISH** and **osmFISH** datasets to identify spatial domains using methods like **MENDER**.  
- Performance evaluation with **Adjusted Rand Index (ARI)** and visualization of clustering results through spatial feature plots.  

---

## Part 1: Single-Cell RNA-Seq Clustering  

### Key Highlights  
- **Leiden Clustering**: Achieved 78.1% accuracy after applying QC, normalization, PCA, and feature selection.  
- **Deviance-based Clustering**: Improved clustering accuracy to 81.7%.  
- **Dimensionality Reduction**:  
  - Designed a Variational Autoencoder (VAE) with an encoder-decoder architecture for latent space representation.  
  - Achieved 87.4% accuracy by leveraging SCVI for modeling latent spaces with a **negative binomial gene likelihood**.  
- **Tools Used**:  
  - **Scanpy** for single-cell analysis, including differential expression and preprocessing.  
  - **SCVI** for advanced modeling and latent space learning.  

---

## Part 2: Imaging-based Spatial Transcriptomics  

### Dataset Descriptions  

#### Dataset 1: MERFISH Mouse Brain (Preoptic Hypothalamus Region)  
- Spatial gene expression from the preoptic hypothalamus region.  
- Contains a spot-gene matrix with spatial (x, y) coordinates.  
- Number of Clusters: 8  

#### Dataset 2: osmFISH Mouse Brain (Somatosensory Cortex Region)  
- Spatial data from the somatosensory cortex region.  
- Includes a spot-gene matrix and spatial coordinates.  
- Number of Clusters: 11  

---

### Methodology  

1. **Preprocessing**:  
   - **Quality Control (QC)**: Filtered poor-quality cells/spots and low-expression genes.  
   - **Normalization**: Addressed sequencing depth differences.  
   - **Feature Selection**: Identified highly variable genes for clustering.  

2. **Dimensionality Reduction**:  
   - Performed PCA to retain significant variance while reducing data dimensions.  

3. **Clustering**:  
   - **Leiden Algorithm**: Effective for identifying spatial communities in single-cell data.  
   - **MENDER**: Optimized for spatial coherence in imaging datasets.  

4. **Visualization**:  
   - Generated spatial feature plots to map clusters to tissue regions.  

5. **Experimentation**:  
   - Tuned parameters like `n_scales` and `nn_mode`. Found that `n_scales=6` with `radius` mode yielded coherent clusters.  

6. **Post-Clustering**:  
   - Standardized cluster labels and saved outputs in the required CSV format.  

---

### Results  

#### **Single-Cell RNA-Seq Data**  
- **Leiden Clustering Accuracy**: 78.1%  
- **Deviance-based Clustering Accuracy**: 81.7%  
- **SCVI Latent Model Accuracy**: 87.4%  

#### **Spatial Transcriptomics**  

| Dataset       | Clustering Method | ARI     | Number of Clusters |  
|---------------|-------------------|---------|--------------------|  
| MERFISH       | MENDER            | 0.48041 | 8                  |  
| osmFISH       | MENDER            | 0.72529 | 11                 |  

---

## Tools and Libraries  

- **Python**: Core language for analysis and modeling.  
- **Scanpy**: Single-cell data preprocessing and clustering.  
- **SCVI**: Dimensionality reduction and probabilistic modeling.  
- **MENDER**: Spatial coherence-aware clustering algorithm.  

---

## How to Run  

1. Clone the repository:  
   ```bash  
   git clone https://github.com/your-username/computational-genomics-clustering.git  
   ```  

2. Navigate to the project directory:  
   ```bash  
   cd computational-genomics-clustering  
   ```  

3. Install dependencies:  
   ```bash  
   pip install -r requirements.txt  
   ```  

4. Run the Jupyter Notebooks:  
   - For single-cell RNA-seq clustering: `Team_1_Part1.ipynb`  
   - For spatial transcriptomics: `Team_2_Part1.ipynb` and `Team_2_Part2.ipynb`  

---

## Future Work  

- Extend SCVI for clustering larger spatial transcriptomics datasets.  
- Experiment with other deep learning-based clustering algorithms for sparse, high-dimensional data.  
- Integrate visualization dashboards for interactive analysis.  

--- 
