# HAM10000 Skin Lesion Classification

## Overview

This project investigates deep learning approaches for multi-class skin lesion classification using the HAM10000 dataset.

The study focuses on how lesion-level data splitting, class imbalance handling, clinical metadata, and prediction uncertainty affect model reliability and generalization.

## Research Question

How do lesion-level data splitting, class-imbalance handling, clinical metadata, and prediction uncertainty affect the reliability and generalization of deep-learning models for multi-class skin-lesion classification?

## Dataset

The project uses the HAM10000 dataset, containing dermoscopic images across seven diagnostic categories:

- akiec — Actinic keratoses / intraepithelial carcinoma
- bcc — Basal cell carcinoma
- bkl — Benign keratosis-like lesions
- df — Dermatofibroma
- mel — Melanoma
- nv — Melanocytic nevi
- vasc — Vascular lesions

The dataset is highly imbalanced, with melanocytic nevi representing the majority class.

Because multiple images can correspond to the same lesion, the project uses lesion-level splitting to reduce data leakage between training, validation, and test sets.

## Methodology

The workflow includes:

- Lesion-level train/validation/test splitting
- Memory-efficient lazy image loading
- Training-only image augmentation
- ResNet50 transfer learning
- Focal loss
- Class weighting
- Balanced sampling
- Two-stage fine-tuning
- EfficientNetB0 comparison
- DenseNet121 comparison
- Clinical metadata fusion as an ablation
- Validation-based model selection
- Locked final test evaluation

## Evaluation

Model performance is evaluated using:

- Accuracy
- Macro F1-score
- Weighted F1-score
- Balanced Accuracy
- Per-class sensitivity
- Per-class specificity
- Area Under the Precision-Recall Curve (AUPRC)

Additional analyses include:

- Monte Carlo Dropout for predictive uncertainty
- Expected Calibration Error (ECE)
- Reliability diagrams
- Grad-CAM visual explanations

## Reproducibility

The notebook uses a fixed random seed and lesion-level data splitting.

The test set is kept separate from model selection and is evaluated only after the final model is selected using validation performance.

## Repository Structure

```text


Important Note

This project is intended for research and educational purposes. The models are not clinical diagnostic tools and should not be used for medical decision-making.

Technologies
Python
TensorFlow / Keras
Scikit-learn
Pandas
NumPy
Matplotlib
Seaborn
HAM10000-Skin-Lesion-Classification/
│
├── HAM10000_Skin_Lesion_Classification_Final_Research.ipynb
└── README.md
