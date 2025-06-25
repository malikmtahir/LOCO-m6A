# Predicting m6A sites with Chromosome-Generalizable Hybrid Deep Features
This repository contains resources related to the research titled **Predicting Tissue-Conserved Human m6A with Chromosome-Generalizable Hybrid Deep Features** In this study, we propose a computational model based on random splitting and Leave-One-Chromosome-Out (LOCO) approaches to identify m6A sites. The proposed framework is built on a detailed architecture that includes core components such as the Data Space, splitting strategies, and Feature Fusion Space.

<pre> ```text LOCO-m6A/ ├── Code/ │ ├── CNN-Fold-Kmer-Onehot-LOCO.ipynb │ └── CNN-Fold-Kmer-Onehot.ipynb ├── Dataset/ │ └── Dataset.rar ├── Figures/ │ ├── Frame_work.jpg │ └── t-SEN.jpg ├── README.md ``` </pre>

## Proposed Framework
### Benchmark Dataset
The m6A benchmark dataset was downloaded from m6A-TCPred, extracting 268,115 base-resolution m6A sites from the m6A-Atlas database. The sites were analyzed across 23 human tissue contexts. The positive dataset had 10,424 highly conserved methylation site sequences across human tissues, while the negative dataset had 54,949 tissue-specific site sequences.

### Splitting Approach
The benchmark dataset for m6A was **randomly split** into:
 - **80%** for the training dataset
  - **20%** for the independent test dataset, ensuring m6A pairs from the same number of chromosomes.
  
  The **Leave-One-Chromosome-Out (LOCO)** approach split the benchmark dataset into 23 sub-datasets:
  - Each chromosome served as the test dataset in one iteration.
  - The remaining 22 chromosomes were used for training.  
- The model was trained on 22 chromosomes and evaluated on the corresponding test dataset.

### Feature Fusion Space
Feature extraction is a crucial step in designing and extracting information patterns from biological sequences. In this work, we employed two feature encoding methods:
-	**k-mer encoding**
- **One-hot encoding with CNN**
The k-mer features were first passed through a dense layer, and then the resulting feature maps were concatenated with the CNN feature maps before further processing

### CNN Model
The **Convolutional Neural Network (CNN)** is specifically designed to capture spatial dependencies in the input data.

<p align="center">
<img src="https://github.com/malikmtahir/LOCO-m6A/blob/main/Figures/Frame_work.jpg" width="500" height="800">

<p align="center">
System model of the ensemble learning framework highlighting data, feature fusion, and model spaces

## Feature Visualization
To visualize the features, we use **t-SNE** to reduce the dimensionality of the **CNN features, k-mer features, k-mer features via Dense layers, and Dense layer features** from the training set. This will allow us to see how the model's learned representations cluster and separate different data points in a 2D space, helping to interpret the feature learning process.

<p align="center">
<img src="https://github.com/malikmtahir/LOCO-m6A/blob/main/Figures/t-SEN.jpg" width="550" height="500">  <p align="right">


### Comparative Analyses against State-of-the-art Models
This comparative study evaluates the developed ensemble model against the cutting-edge model **m6A-TCPred [1]** focusing on the m6A sites identification problem.
  
### Statistical Analyses
The statistical analysis is based on the **standard error method** that computes the **mean, standard deviation, critical value** (i.e., **z-score**), and **95% confidence interval** for a sample of **accuracy, sensitivity, specificity, MCC,** and **AUC-ROC**. These analyses aim to validate the quantitative results agains the **CNN** model.

  
# References 
The following references are utlized in the comparative analyses.

[1]. Tu, G., Wang, X., Xia, R. and Song, B., 2024. m6A-TCPred: a web server to predict tissue-conserved human m6A sites using machine learning approach. BMC bioinformatics, 25(1), p.127.


# Contact details
## Muhammad Tahir (m.tahir-ra@uwinnipeg.ca)
### Affiliation:
1. **Department of Applied Computer Science, The University of Winnipeg, 515 Portage Ave, R3B 2E9, MB, Canada**
2. **Department of Computer Science, Abdul Wali Khan University, Mardan, Mardan, 23200, Pakistan**

## Qian Liu (qi.liu@uwinnipeg.ca)
### Affiliation:
1. **Department of Applied Computer Science, The University of Winnipeg, 515 Portage Ave, R3B 2E9, MB, Canada**
