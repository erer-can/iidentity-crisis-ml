# Multimodal Fruit & Vegetable Recognition

This repository contains two machine learning assignments built on a **handcrafted multimodal dataset** for fruit and vegetable recognition.  
The work was carried out as part of a team named **IIDentity Crisis**, which refers to the *project group*, not the dataset itself.

The repository consolidates **supervised** and **unsupervised** learning experiments into a single, coherent machine learning case study.

---

## Project Overview

The project addresses a multimodal classification problem where visual information alone is often insufficient due to strong inter-class similarity. To mitigate this, the dataset combines:

- **Images** (real-world and carefully filtered synthetic samples)
- **Textual descriptions** (automatically generated and masked to prevent label leakage)
- **Categorical metadata** (origin, climate, harvest period)

All data was **collected, generated, cleaned, and validated manually by the authors**, resulting in a fully controlled and reproducible dataset.

---

## Dataset Construction (Assignment 1)

The dataset was constructed from scratch and contains **3,092 labeled samples** across five classes:
- apple
- banana
- cucumber
- eggplant
- tangerine

### Data Sources
- **Real images**: Personally collected under natural lighting conditions (50–60 per class)
- **Synthetic images**: Generated using multiple diffusion models and manually filtered
- **Text modality**: Generated using a vision–language model and masked to prevent explicit class leakage
- **Categorical attributes**: Probabilistically generated with controlled semantic noise

Dimensionality reduction (PCA) is applied to high-dimensional handcrafted image descriptors to satisfy feature constraints and suppress redundancy.

Full dataset design, statistics, and quality-control procedures are documented in the Assignment 1 report.

---

## Assignment Breakdown

### Assignment 1 — Supervised Multimodal Learning

Focuses on **from-scratch implementation** and evaluation of a regularized multiclass logistic regression model.

Key components:
- Handcrafted image descriptors (HOG, HSV, LBP, Hu moments, BoVW)
- TF–IDF text features with controlled vocabulary size
- One-hot encoded categorical metadata
- Early multimodal feature fusion
- Similarity analysis and outlier detection
- Comparison against scikit-learn implementation

Notebook:
- `src/CMPE462_assignment1.ipynb`

Report:
- `docs/IIDentity_Crisis_Assignment1.pdf`

---

### Assignment 2 — Unsupervised Analysis & Representation Study

Explores the structure of the same handcrafted dataset using unsupervised techniques.

Key components:
- Dimensionality reduction and visualization
- Clustering and qualitative structure analysis
- Interpretation of class overlap and failure modes

This assignment is accompanied by:
- A short written report
- A **1-hour recorded discussion video** explaining methodology, results, and insights

Notebook:
- `src/CMPE462_assignment2.ipynb`

Report:
- `docs/IIDentity_Crisis_Assignment2.pdf`

---

## Repository Structure

```
.
├── docs
│   ├── IIDentity_Crisis_Assignment1.pdf
│   └── IIDentity_Crisis_Assignment2.pdf
├── src
│   ├── CMPE462_assignment1.ipynb
│   └── CMPE462_assignment2.ipynb
├── README.md
├── .gitignore
└── LICENSE

```

---

## How to Use

1. Follow the dataset access instructions provided in the **Assignment 1 report**.
2. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
3. Run the notebooks independently:
   - Assignment 1 for supervised experiments
   - Assignment 2 for unsupervised analysis

All preprocessing, feature extraction, and training steps are documented inline.

---

## Reproducibility Notes

- All dataset splits use fixed random seeds.
- Feature extraction, PCA, and model training are performed strictly within training splits.
- Minor numerical differences may occur across environments.

---

## License

Provided for educational and portfolio purposes.
