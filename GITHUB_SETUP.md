# GitHub Repository Setup Guide

## Recommended Repository Name

`brain-tumor-mri-classification`

## Method 1 — Git Commands

### 1. Create an empty repository on GitHub

On GitHub:

1. Click **New repository**
2. Repository name: `brain-tumor-mri-classification`
3. Choose **Public** or **Private**
4. Do not add another README if you are uploading this prepared repository
5. Click **Create repository**

### 2. Extract this ZIP

Extract:

`brain-tumor-mri-classification_GitHub_Ready.zip`

Open a terminal inside the extracted `brain-tumor-mri-classification` folder.

### 3. Initialize Git

```bash
git init
git add .
git commit -m "Initial commit: Brain Tumor MRI classification project"
```

### 4. Set the main branch

```bash
git branch -M main
```

### 5. Connect your GitHub repository

Replace `YOUR_USERNAME` with your GitHub username:

```bash
git remote add origin https://github.com/YOUR_USERNAME/brain-tumor-mri-classification.git
```

### 6. Push

```bash
git push -u origin main
```

## Method 2 — GitHub Website Upload

For a simple first upload:

1. Create the empty GitHub repository.
2. Open it in the browser.
3. Select **Add file → Upload files**.
4. Drag the contents of the extracted repository into GitHub.
5. Enter a commit message.
6. Click **Commit changes**.

For many files and future teamwork, Git commands or GitHub Desktop are better.

## Team Workflow

Each member can work on a branch:

```bash
git checkout -b member-name
```

Example:

```bash
git checkout -b senanayake-svm
```

After changes:

```bash
git add .
git commit -m "Update SVM model notebook"
git push -u origin senanayake-svm
```

Then create a Pull Request on GitHub and merge it into `main`.

## Suggested Branch Names

```text
hettiarachchi-efficientnet
thennakoon-mlp
senanayake-svm
weerakkody-cnn
malintha-efficientnet
somarathne-densenet
```

## Do Not Upload

Avoid committing:

- the full Kaggle MRI dataset,
- virtual environments,
- temporary Colab files,
- TensorFlow checkpoints,
- large `.keras` / `.h5` / `.joblib` model files through normal Git.

GitHub rejects normal files larger than 100 MB.

## If You Need to Store a Large `.keras` Model

### Option A — Git LFS

Install Git LFS, then:

```bash
git lfs install
git lfs track "*.keras"
git lfs track "*.h5"
git lfs track "*.joblib"
git add .gitattributes
```

Remove the model patterns from `.gitignore` only if you intentionally use Git LFS.

Then:

```bash
git add path/to/model.keras
git commit -m "Add trained model with Git LFS"
git push
```

### Option B — GitHub Release

Keep model files out of the repository and attach the final trained model to a GitHub Release.

This is often simpler for a university project.

## Open a Notebook from GitHub in Colab

After pushing to GitHub, a notebook can be opened using:

```text
https://colab.research.google.com/github/YOUR_USERNAME/brain-tumor-mri-classification/blob/main/notebooks/models/NOTEBOOK_NAME.ipynb
```

Replace `YOUR_USERNAME` and `NOTEBOOK_NAME`.

## Recommended Final Checks Before Submission

- README displays correctly.
- All six owner/model names are correct.
- All notebooks open without missing cells.
- Dataset is downloaded through KaggleHub rather than committed.
- Final result CSV files match the latest executed notebooks.
- No manually altered metrics are committed.
- Final model selection uses Validation Macro F1.
- The report and GitHub repository use the same owner/model mapping.
