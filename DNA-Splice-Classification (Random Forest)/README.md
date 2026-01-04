# DNA Splice-Junction Classification using Random Forest

## Project Overview
In this project, I built a machine learning pipeline to classify DNA sequences from the **UCI Molecular Biology dataset**. The goal is to identify boundaries between exons (coding regions) and introns (non-coding regions), specifically looking for **EI (Extron-Intron)** and **IE (Intron-Exon)** splice sites.


## The Dataset
The dataset consists of 3,190 DNA sequences, each 60 base-pairs long. 
- **Classes:** Primate splice junctions (EI), (IE), or Neither (N).
- **Features:** Categorical DNA nucleotides (A, C, G, T).

## Key Challenges & Solutions
1. **Data Cleaning & Splitting**
The raw DNA was in one long string of 60 characters. I split these into 60 separate columns so the model could look at each position individually. I also cleaned up the "messy" data by replacing 'D' with 'N' and then removing any rows with 'N' so the model only learned from clear A, C, G, T sequences.

2. **Encoding**
Features (X): I used **One-Hot Encoding** for the DNA bases.
Target (y): I used **Label Encoding** to turn the class names (EI, IE, N) into numbers (0, 1, 2).

3. **Tuning the Model**
I used **GridSearchCV** to find the best settings for my Random Forest. This helped me pick the best max_depth and number of trees (n_estimators) to get the highest accuracy.

## Results
The model worked really well! When I plotted the Feature Importance, there was a huge spike around **Position 30**. This makes total sense because that’s exactly where the DNA "cut" happens in the sequences.

## Technologies Used
- **Python**
- **Pandas/NumPy** (Data Manipulation)
- **Scikit-Learn** (Random Forest, OneHotEncoding, LabelEncoder, GridSearch)
- **Matplotlib** (Data Visualization)

## Credits & Data Source
This project uses the **Splice-Junction Gene Sequences** dataset from the **UCI Machine Learning Repository**. 

* **Source:** [UCI Machine Learning Repository - Molecular Biology](https://archive.ics.uci.edu/ml/datasets/Molecular+Biology+(Splice-Junction+Gene+Sequences))
