# Predicting m6A sites with Chromosome-Generalizable Hybrid Deep Features
This repository contains resources related to the research titled **Predicting Tissue-Conserved Human m6A with Chromosome-Generalizable Hybrid Deep Features** In this study, we propose a computational model based on random splitting and Leave-One-Chromosome-Out (LOCO) approaches to identify m6A sites. The proposed framework is built on a detailed architecture that includes core components such as the Data Space, splitting strategies, and Feature Fusion Space.

## Proposed Framework
### Benchmark Dataset
The **Data Space** represents the continuous nature of DNA and RNA sequences and emphasizes the necessity of transforming these continuous chains into **semantic vector representations** through **tokenization and vectorization** processes. 

### Feature Fusion Space
The m6A benchmark dataset was downloaded from m6A-TCPred, extracting 268,115 base-resolution m6A sites from the m6A-Atlas database. The sites were analyzed across 23 human tissue contexts. The positive dataset had 10,424 highly conserved methylation site sequences across human tissues, while the negative dataset had 54,949 tissue-specific site sequences.

### Splitting Approach
The benchmark dataset for m6A was **randomly split** into:
 - **80%** for the training dataset
  - **20%** for the independent test dataset, ensuring m6A pairs from the same number of chromosomes.
  
  The **Leave-One-Chromosome-Out (LOCO)** approach split the benchmark dataset into 23 sub-datasets:
  - Each chromosome served as the test dataset in one iteration.
  - The remaining 22 chromosomes were used for training.  
- The model was trained on 22 chromosomes and evaluated on the corresponding test dataset.



<p align="center">
<img src="https://github.com/shahid3167/Ensemble_Learning_with_Semantic_Feature_Fusion/blob/ca8c6adafb0b3b6ca913754e6ebf90237e1122f1/Figures/SystemModel.jpg" width="700" height="500">

<p align="center">
System model of the ensemble learning framework highlighting data, feature fusion, and model spaces

## Results
The developed framework is applied to three (**C. elegans, D. melanogaster, and H. sapiens**) datasets (available in the dataset folder) and the tendency of the **correlated features** and **non-related features** is presented through a **Bland-Altman plot**, followed by the overall feature representations, which are categorized into correlated and non-related features, for the three datasets. Subsequently, the results are evaluated under several different scenarios against the individual models (FCN, CCN, GRU, and LSTM) and state-of-the-art DNA identification models, followed by statistical evaluation using mean, standard deviation, and 95% confidence interval.

### Tendency of the Correlated and Non-Related Features

<p align="center">
<img src="https://github.com/shahid3167/Ensemble_Learning_with_Semantic_Feature_Fusion/blob/c03e3790d62624efb3403b3f2d6770526188f908/Figures/BlandAltmanPlotFeatures.jpg" width="550" height="350">  <p align="right">

<p align="center">
Bland Altman plot highlighting the tendency of the correlated and non-related features 

<p align="center">
<img src="https://github.com/shahid3167/Ensemble_Learning_with_Semantic_Feature_Fusion/blob/e9b69355fcfe8c34e82d10be80d9c009ce212e09/Figures/FeatureFrequencies.jpg" width="550" height="350">

<p align="center">
Categorization of the features into semantically correlated and non-related features  

### With and Without Semantic Fusion
To highlight the **impact of semantic feature fusion**, a **with and without feature fusion** evaluation is conducted on the developed **ensemble learning framework**. The results showcased a significant influence on various performance metrics (**Accuracy, Sensitivity, and Specificity**) across the **C. elegans, D. melanogaster, and H. sapiens**  datasets.

<p align="center">
<img src="https://github.com/shahid3167/Ensemble_Learning_with_Semantic_Feature_Fusion/blob/a007c764193dbd6663d3648de1d0d75cfffd9197/Figures/WithWithoutFusion_Accuracy.jpg" width="700" height="300">

<p align="center">
Performance evaluation of the ensemble learning framework considering with and without semantic feature fusion

### Comparative Analyses against Individual Models
This comparative study evaluates the performance of the developed ensemble model through accuracy, sensitivity, specificity, and MCC against the individual models FCN, CNN, GRU, and LSTM.

<p align="center">
<img src="https://github.com/shahid3167/Ensemble_Learning_with_Semantic_Feature_Fusion/blob/2433d1ccd72848a96ab1578dd7ae25d1a5815557/Figures/AverageComparativeStudy.jpg" width="700" height="300">

<p align="center">
  Comparative study of the ensemble model against individual models  

### Comparative Analyses against State-of-the-art Models
This comparative study evaluates the developed ensemble model against the cutting-edge models **iNuc-PseKNC [49]**, **iNuc-STNC [50]**, and **NP_CBiR [54]**, focusing on the DNA sequence identification problem.

<p align="center">
<img src="https://github.com/shahid3167/Ensemble_Learning_with_Semantic_Feature_Fusion/blob/05b813c012d0054adcb59afd993ca4307e35cb73/Figures/AverageComparativeStudyWithOtherModels.jpg" width="700" height="300">

<p align="center">
  Comparative study of the ensemble model against state-of-the-art models 

  
### Statistical Analyses
The statistical analysis is based on the **standard error method** that computes the **mean, standard deviation, critical value** (i.e., **z-score**), and **95% confidence interval** for a sample of **accuracy, sensitivity, specificity, MCC,** and **AUC-ROC**. These analyses aim to validate the quantitative results against the individual **FCN, CNN, GRU**, and **LSTM** models, respectively.

<p align="center">
Statistical analyses highlighting mean, standard deviation, and 95% confidence interval for various models.
<p align="center">
<img src="https://github.com/shahid3167/Ensemble_Learning_with_Semantic_Feature_Fusion/blob/a8ab126280bf068166d92b26a81fc86bf21f0e14/Figures/Statistical_Analysis.jpg" width="700" height="400">
  
# References 
The following references are utlized in the comparative analyses.

[49]. Shou-Hui Guo, En-Ze Deng, Li-Qin Xu, Hui Ding, Hao Lin, Wei Chen, and Kuo-Chen Chou. inuc-pseknc: a sequence-based predictor for
predicting nucleosome positioning in genomes with pseudo k-tuple nucleotide composition. Bioinformatics, 30(11):1522–1529, 2014.

[50].  Muhammad Tahir and Maqsood Hayat. inuc-stnc: a sequence-based predictor for identification of nucleosome positioning in genomes by extending the concept of saac and chou’s pseaac. Molecular BioSystems, 12(8):2587–2593, 2016.

[54]. Guo-Sheng Han, Qi Li, and Ying Li. Nucleosome positioning based on dna sequence embedding and deep learning. BMC genomics, 23
(Suppl 1):301, 2022.

# Contact details
## Dr. Shahid Hussain (shahid.hussain@mu.ie)
### Affiliation:
1. **National University of Ireland Maynooth (NUIM), Maynooth, Co. Kildare, W23 F2H6, Ireland**
2. **Department of Computing, South East Technological University (SETU), Carlow Campus, Carlow, R93 V960, Ireland**

## Dr. Muhammad Tahir (m.tahir@umanitoba.ca)
### Affiliation:
1. **Department of Electrical and Computer Engineering, University of Manitoba, Winnipeg, Manitoba, R3T5V6, Canada**
2. **Department of Computer Science, Abdul Wali Khan University, Mardan, Mardan, 23200, Pakistan**
