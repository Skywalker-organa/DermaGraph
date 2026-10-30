# ቃ DermaGraph
> **Multimodal Spatial Graph Convolutional Networks (GCN) for Genomically-Informed Melanoma Diagnostics**

DermaGraph is an advanced deep learning framework designed to predict critical melanoma genomic driver mutations (including **BRAF**, **NRAS**, and **TP53**) directly from Whole Slide Images (WSIs) by tiling WSIs into spatial grids, extracting ResNet50 visual embeddings, and constructing spatial graph architectures.

---

## ቀ Project Overview
- **Modality 1 (Histopathology):** Spatial Graph representation over millions of deep feature embeddings extracted from localized tissue patches.
- **Modality 2 (Clinical Profiles):** Multi-layer MLP networks fusing clinical tabular covariates and demographics.
- **Deep Learning Architecture:** Multi-Task Spatial Graph Convolutional Network (GCN) with dual global-mean and focal-maximum poolings.

---

## ቅ Repository Structure
```bash
└── src/
│   └── slide_gcn_pipeline.py      # Core Graph Deep Learning pipeline & GCN architectures
└── results/
│   └── full_cohort_5fold_metrics.csv       # Overall 5-Fold cross validation metrics
│   └── subset_21_30_evaluation_report.csv  # Diagnostic confidence reports per-patient
└── README.md                               # Project documentation and performance metrics
```

---

## ቄ Overall Performance (5-Fold Cross Validation)

Our GCN achieves exceptional visual-to-genomic translation on the **TCGA-SKCM** cutaneous melanoma cohort:

| Target Mutation | Accuracy | Precision | Recall | F1-Score | AUROC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **BRAF Hotspot** | **89.70%** | **91.10%** | **89.30%** | **0.909** | **0.981** |
| **NRAS Hotspot** | **78.40%** | **80.00%** | **75.10%** | **0.774** | **0.864** |
| **TP53 Nonsilent** | **88.90%** | **83.30%** | **81.00%** | **0.821** | **0.912** |

---

## ቇ Getting Started

### 1. Requirements
```bash
pip install openslide-python torch torchvision pandas scikit-learn transformers
apt-get install openslide-tools
```

### 2. Execution
To execute model training and run evaluation cross-validation:
```bash
python src/slide_gcn_pipeline.py
```
