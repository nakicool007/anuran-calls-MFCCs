# Homework 7

**Name:** Nakul Kumbria  
**GitHub Username:** nakicool007  
**USC ID:** 6748597520

This homework uses the Anuran Calls (MFCCs) dataset for SVM classification and k-means clustering. It also includes a hierarchical clustering problem using a four-observation dissimilarity matrix.

## Folder structure

```text
.
├── README.md
├── .gitignore
├── data
│   └── anuran_calls_data
│       ├── Frogs_MFCCs.csv
│       └── Readme.txt
├── notebook
│   └── Kumbria_Nakul_HW7.ipynb
└── requirements.txt
```

All solution code, explanations, results, and plots are in the notebook. The local `.venv` folder is excluded by `.gitignore`.

## Setup

The notebook was run with Python 3.14. Create a virtual environment from the project folder:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Open `notebook/Kumbria_Nakul_HW7.ipynb` in VS Code or another notebook editor and select the `.venv` Python kernel. Run the cells from top to bottom. The data paths work when the working directory is either the project folder or the `notebook` folder.

## Questions

1. **SVM classification:** predict Family, Genus, and Species using one-versus-rest Gaussian-kernel and L1-penalized linear SVMs. Select parameters with 10-fold cross-validation, compare raw and standardized features, and use balanced class weights to address imbalance. Evaluate with exact match and Hamming measures.
2. **K-means clustering:** use all observations and repeat the procedure 50 times. Select k using the Calinski-Harabasz score, assign majority labels within each cluster, and report the mean and standard deviation of the Hamming measures.
3. **Hierarchical clustering:** calculate the complete- and single-linkage merges, draw the dendrograms, identify the two-cluster cuts, and draw an equivalent reordered tree.

The SVM searches and 50 clustering trials can take several minutes. Saved outputs are included in the notebook. Seeds are fixed to make the calculations reproducible.

## Dataset

Source: [UCI Anuran Calls (MFCCs)](https://archive.ics.uci.edu/dataset/406/anuran+calls+mfccs), DOI: 10.24432/C5CC9H.

The dataset contains 7,195 observations, 22 MFCC features, and three categorical labels. `RecordID` is excluded from the predictors. The original dataset description is in `data/anuran_calls_data/Readme.txt`.
