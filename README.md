# Brain Tumor Classification Using MRI Images

AI/ML group project for **IT2011 – Artificial Intelligence and Machine Learning, Year 2 Semester 1 (2026), SLIIT**.

The project classifies brain MRI images into four classes:

- Glioma
- Meningioma
- No Tumor
- Pituitary

## Current Model Ownership

| Student | IT Number | Assigned Model |
|---|---|---|
| Hettiarachchi H.A.A.S | IT25104064 | EfficientNetB0 |
| Thennakoon T.M.A.N | IT25100854 | MLP |
| Senanayake S.M.K.D | IT25100233 | SVM |
| Weerakkody W.W.M.B | IT25101776 | Custom CNN |
| Malintha K.K.I | IT25102346 | EfficientNetB0 |
| Somarathne R.N.N | IT25100295 | DenseNet121 |

> Note: The ownership list supplied by the group assigns **EfficientNetB0 to two students**. The repository preserves that mapping exactly.

## Dataset

Kaggle dataset used by the notebooks:

`maleeshaweerakkody/brain-tumor-mri-preprocessed`

The notebooks download the dataset with `kagglehub`, so the image dataset is **not stored in this GitHub repository**.

## Preprocessing Pipeline

The project preprocessing pipeline includes:

1. Data cleaning and duplicate checking
2. Train/Test leakage checking
3. Stratified Training/Validation preparation
4. Aspect-ratio preserving resize and padding to 224×224
5. CLAHE enhancement
6. Model-specific normalization
7. Training-only augmentation
8. Training-only class balancing
9. HOG + GLCM + StandardScaler + PCA for the feature-based branch

## Model Selection

Each model trains two variants.

The better variant is selected using:

**Validation Macro F1**

The Official Test set is used only after variant selection for final evaluation.

Reported metrics include:

- Accuracy
- Precision
- Recall
- Macro F1
- Confusion Matrix
- Classification Report

## Repository Structure

```text
brain-tumor-mri-classification/
├── README.md
├── requirements.txt
├── .gitignore
├── CONTRIBUTORS.md
├── GITHUB_SETUP.md
├── data/
│   └── README.md
├── docs/
│   └── MODEL_OWNER_MANIFEST.csv
├── notebooks/
│   ├── preprocessing/
│   │   └── 00_Group_Preprocessing_and_EDA.ipynb
│   ├── models/
│   │   ├── 01_IT25104064_Hettiarachchi_EfficientNetB0_ImageNet_2Variants.ipynb
│   │   ├── 02_IT25100854_Thennakoon_MLP_HOG_GLCM_PCA_2Variants.ipynb
│   │   ├── 03_IT25100233_Senanayake_SVM_Linear_2Variants.ipynb
│   │   ├── 04_IT25101776_Weerakkody_CustomCNN_2Variants.ipynb
│   │   ├── 05_IT25102346_Malintha_EfficientNetB0_ImageNet_2Variants.ipynb
│   │   └── 06_IT25100295_Somarathne_DenseNet121_ImageNet_2Variants.ipynb
│   └── comparison/
│       └── 07_Final_6_Owner_Model_Comparison.ipynb
├── results/
│   └── README.md
└── deployment/
    └── README.md
```

## Run in Google Colab

1. Open any `.ipynb` file from the `notebooks/` folder.
2. Click **Open in Colab**, or upload the notebook to Google Colab.
3. For pretrained CNN models, use:
   - `Runtime` → `Change runtime type` → `T4 GPU`
4. Run cells from top to bottom.
5. The notebook downloads the required dataset automatically.

## Install Locally

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

macOS/Linux:

```bash
source .venv/bin/activate
```

Install packages:

```bash
pip install -r requirements.txt
```

Then start Jupyter:

```bash
jupyter notebook
```

## Important GitHub File-Size Note

Do **not** commit the full MRI dataset or large trained model files directly to normal Git.

Files such as:

- `*.keras`
- `*.h5`
- `*.joblib`
- dataset ZIPs

are ignored by default.

For final model binaries, use **Git LFS**, a **GitHub Release**, or another approved storage method.

## Academic Use

This repository is for an academic AI/ML project. The MRI classifier is for educational/research use and is **not a medical diagnosis system**.
