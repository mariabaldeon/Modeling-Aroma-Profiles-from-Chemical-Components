# Modeling-Aroma-Profiles-from-Chemical-Components

Accurately predicting the aroma of a molecule based on its chemical structure is a promising direction for advancing the development of flavors and fragrances in the food, cosmetic, and pharmaceutical industries. This study explores the potential of machine learning (ML) techniques to predict aroma descriptors from molecules encoded in SMILES format. A newly curated dataset was developed, comprising 5,855 molecules annotated with 44 standardized odor descriptors. Three models were evaluated on this dataset, namely Random Forest, XGBoost, and TabNet. Molecular feature extraction was conducted using Morgan Fingerprints, and the influence of fingerprint radius on predictive performance was assessed. To address the significant label imbalance, the MLSMOTE data augmentation strategy was also evaluated. Among the tested models, XGBoost trained on an MLSMOTE-augmented dataset with a fingerprint radius of 3 demonstrated the highest predictive performance. It achieved an AUROC of 0.954, a precision of 0.803, a recall of 0.691, and an F1-score of 0.742. In contrast, TabNet consistently underperformed across all configurations, with statistically lower F1-scores compared to the other two ML models. External validation using a cacao-specific molecule dataset revealed a distribution shift between training and test sets, resulting in reduced precision but high recall. Retraining XGBoost directly on the cacao dataset eliminated this performance degradation and significantly improved all evaluation metrics. These findings demonstrate that machine learning models, particularly XGBoost, can effectively predict sensory attributes from molecular structure. This approach offers a reliable and data-driven alternative for accelerating aroma design and reducing subjectivity in product development across sensory-driven industries. 

# Dataset
The dataset used in this study was constructed by integrating public sources. Public datasets were obtained from ChemTasteDB, FlavorDB, GoodScents, IFRA_2019, Keller, Leffingwell, and Sharma_2021b, all available through the Pyrfume public data archive (Pyrfume, 2024). Moreover, datasets provided by (León Junca et al., 2023) that contained aroma information from distilled rum and gin are also included. The initial compilation yielded a comprehensive dataset of 361,640 molecules. For each molecule, relevant information was collected, including the CAS number, compound name, IUPAC name, PubChem CID, SMILES notation, and associated odor descriptors.

 <img width="124" height="494" alt="image" src="https://github.com/user-attachments/assets/8e013e48-64dd-4095-8178-8a2f2d22db1c" />
 
Figure 1. Preprocessing steps for the newly curated QSOR dataset.

Preprocessing was conducted in several stages, as illustrated in Fig. 1. First, duplicate entries and incomplete records were removed, resulting in the elimination of 379 molecules. The SMILES (Simplified Molecular Input Line Entry System) notation for each molecule was then standardized. SMILES provides a linear representation of molecular structure using ASCII characters. Two types of SMILES are commonly used, corresponding to canonical SMILES and isomeric SMILES. Canonical SMILES describe the basic 2D structure of a molecule, while isomeric SMILES include stereochemistry and isotope information, offering a richer description of the 3D molecular structure (David et al., 2020) [16]. Using the PubChemPy Python library, all canonical SMILES were converted to isomeric format, and existing isomeric SMILES were verified for consistency.



# Citation
If you use this code in your research, please cite our paper.
```
@article{
title = {Unveiling Aroma: A Machine Learning Approach to Modeling Aroma Profiles from Chemical Components<img width="468" height="75" alt="image" src="https://github.com/user-attachments/assets/0182ed6e-afdd-4469-8c85-480391d746bb" />
},
author = {Maria Baldeon-Calisto and Francisco Rivera-Velastegui and Susana K. Lai-Yuen and Daniel Riofrío and Noel Pérez-Pérez and Diego Benítez and Ricardo Flores-Moyano}}
```
