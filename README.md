Predicting m6A sites with Chromosome-Generalizable Hybrid Deep Features
This repository contains resources related to the research titled Predicting Tissue-Conserved Human m6A with Chromosome-Generalizable Hybrid Deep Features. In this study, we propose a computational model based on random splitting and Leave-One-Chromosome-Out (LOCO) approaches to identify m6A sites. The proposed framework is built on a detailed architecture that includes core components such as the Data Space, splitting strategies, and Feature Fusion Space.
Proposed Framework
Benchmark Dataset
The study used the m6A benchmark dataset from m6A-TCPred, extracting 268,115 base-resolution m6A sites from the m6A-Atlas database. The sites were analyzed across 23 human tissue contexts. The positive dataset had 10,424 highly conserved methylation site sequences across human tissues, while the negative dataset had 54,949 tissue-specific site sequences. 

Splitting Approach
• The benchmark dataset for m6A was randomly split into:
•	80% for the training dataset
•	20% for the independent test dataset, ensuring m6A pairs from the same number of chromosomes.
• The Leave-One-Chromosome-Out (LOCO) approach split the benchmark dataset into 23 sub-datasets:
•	Each chromosome served as the test dataset in one iteration.
•	The remaining 22 chromosomes were used for training.
•	The model was trained on 22 chromosomes and evaluated on the corresponding test dataset.


Feature Fusion Space
Feature extraction is a crucial step in designing and extracting information patterns from biological sequences. In this work, we employed two feature encoding methods:
•	k-mer encoding
•	One-hot encoding with CNN
The k-mer features were first passed through a dense layer, and then the resulting feature maps were concatenated with the CNN feature maps before further processing

 Model Space
The Model Space presents a mathematical framework for the individual models used in this study, primarily focusing on the Convolutional Neural Network (CNN). The CNN is specifically designed to capture spatial dependencies in the input data.

