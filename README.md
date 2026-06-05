# Belajar Machine Learning — Final Project (BMLP)

[![license](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE) [![notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)]

Short summary
---------------
This repository contains the final project for the "Belajar Machine Learning Untuk Pemula" course. It demonstrates practical workflows for both clustering and classification using Jupyter notebooks, example CSV datasets, and several pre-trained model artifacts exported in HDF5 format. The notebooks are the source of truth for data preparation, model training, evaluation, and export steps.

Table of contents
------------------
- [Overview](#overview)
- [Demo (workflow diagram)](#demo-workflow)
- [Project structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage examples](#usage-examples)
- [Files of interest](#files-of-interest)
- [Contributing](#contributing)
- [License & contact](#license--contact)

Overview
--------
The work includes two primary Jupyter notebooks that implement end-to-end experiments:

- Classification: preprocessing, model selection/tuning, training, and evaluation.
- Clustering: data exploration, PCA, clustering model training, and result analysis.

All steps are executed interactively in the notebooks and reference the CSV datasets included in this folder. Trained models are provided as `.h5` files so you can load them quickly for inference or further fine-tuning.

Demo (workflow)
----------------
The high-level workflow is:

```mermaid
flowchart LR
A[CSV datasets] --> B[Notebooks - preprocessing]
B --> C[Train-Validate-Test split]
C --> D[Model training]
D --> E[Evaluation and reports]
E --> F[Export artifacts (.h5, PCA, tuned models)]
```

Project structure
------------------
Top-level files and folders (this repository root):

```text
[Clustering]_Submission_Akhir_BMLP_Ahmad_Meijlan_Yasir.ipynb
[Klasifikasi]_Submission_Akhir_BMLP_Ahmad Meijlan Yasir.ipynb
data_clustering.csv
data_clustering_inverse.csv
decision_tree_model.h5
explore_random_forest_classification.h5
model_clustering.h5
PCA_model_clustering.h5
tuning_classification.h5
README.md
LICENSE
```

Prerequisites
-------------
- Python 3.8+ (3.10 recommended)
- `pip` and a virtual environment tool (venv or conda)
- Optional: GPU for faster model training (if you plan to retrain)

Installation
------------
Create and activate a Python virtual environment, then install dependencies from the provided `requirements.txt`. Example (Windows PowerShell):

```powershell
python -m venv venv
venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

The included `requirements.txt` pins a set of commonly used packages for these notebooks (numpy, pandas, scikit-learn, matplotlib, seaborn, jupyterlab, tensorflow, keras). Adjust versions if you have environment constraints (GPU driver, CUDA, etc.).

Usage examples
--------------
- Open a notebook in JupyterLab or Jupyter Notebook and run all cells in order:

	- ` [Klasifikasi]_Submission_Akhir_BMLP_Ahmad Meijlan Yasir.ipynb` — classification workflow
	- ` [Clustering]_Submission_Akhir_BMLP_Ahmad_Meijlan_Yasir.ipynb` — clustering workflow

- Load a provided Keras model in Python:

```python
from tensorflow.keras.models import load_model
model = load_model('decision_tree_model.h5')
preds = model.predict(X_sample)
```

- Load a CSV for quick inspection:

```python
import pandas as pd
df = pd.read_csv('data_clustering.csv')
df.head()
```

Files of interest
-----------------
- Notebooks:
	- ` [Klasifikasi]_Submission_Akhir_BMLP_Ahmad Meijlan Yasir.ipynb` — classification experiment and tuning.
	- ` [Clustering]_Submission_Akhir_BMLP_Ahmad_Meijlan_Yasir.ipynb` — clustering experiment with PCA.
- Data:
	- `data_clustering.csv`, `data_clustering_inverse.csv` — datasets used by clustering notebook.
- Model artifacts:
	- `decision_tree_model.h5`, `explore_random_forest_classification.h5`, `model_clustering.h5`, `PCA_model_clustering.h5`, `tuning_classification.h5`

Notes
-----
- The Jupyter notebooks are the authoritative source for preprocessing steps, model hyperparameters, training logs, and evaluation metrics. If you want to reproduce experiments exactly, run the notebooks from top to bottom in a fresh environment.

Contributing
------------
Contributions and suggestions are welcome. Recommended workflow:

1. Fork the repository and create a branch: `git checkout -b feature/your-change`
2. Make changes in the notebooks or add new scripts.
3. Re-run affected notebooks to ensure results are reproducible.
4. Submit a pull request with a clear description of changes.

License & contact
------------------
This project is distributed under the MIT License — see the `LICENSE` file.

Project owner:

- Name: Ahmad Meijlan Yasir
- Email: yasirahmad220504@gmail.com

