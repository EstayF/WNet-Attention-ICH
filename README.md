# WNet-Attention-ICH

Official implementation of the paper  
**"Unsupervised Dual-Task W-Net with Spatial Attention for Intracranial Hemorrhage Detection and Segmentation"** (ICPRS 2025).

---

## 🧠 Overview
This repository provides the code, structure, and setup to reproduce the experiments presented in the ICPRS 2025 paper.  
The proposed unsupervised pipeline integrates preprocessing, attention-based modeling, and postprocessing into a coherent framework for early epidural hemorrhage (EDH) screening in non-contrast CT (NCCT).  
It reinforces the potential of annotation-free deep learning methods to support medical image analysis in resource-limited environments.

Pipeline: preprocessing → attention-based W-Net (Soft-N-Cut + 1–SSIM) → postprocessing.

---

## 🚀 Step-by-Step Usage

Follow these steps to reproduce the experiments from the paper.

### 1️⃣ Clone the repository
```bash
git clone https://github.com/<tu-usuario>/WNet-Attention-ICH.git
cd WNet-Attention-ICH
```

### 2️⃣ Create and activate a virtual environment
```bash
python -m venv env
source env/bin/activate      # On Windows: env\Scripts\activate
```

### 3️⃣ Install dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ Prepare datasets
Download the following datasets manually and organize them as:

```
data/
├── RSNA_EDH/
│   ├── train/
│   └── val/
└── BHSD_EDH/
    ├── test/
    └── masks/
```

- **RSNA ICH (2019):** https://www.kaggle.com/c/rsna-intracranial-hemorrhage-detection
- **BHSD (2023):** https://bhsd-dataset.github.io

### 5️⃣ Run preprocessing
```bash
python src/preprocess.py --input data/RSNA_EDH/train --output data/preprocessed
```

### 6️⃣ Train the model
```bash
python src/train_unsupervised.py --data_dir data/preprocessed --epochs 200
```

### 7️⃣ Evaluate results
```bash
python src/evaluate.py --test_dir data/BHSD_EDH
```

### 8️⃣ Visualize outputs
```bash
python src/visualize_results.py --input results/
```

---

## 💡 Tips
- All parameters can be adjusted via command-line flags (use `--help`).
- You can also run the code in Google Colab or Kaggle Notebooks by cloning this repo.

---

## 📊 Datasets

- **RSNA Intracranial Hemorrhage Detection (2019)** — used for training with epidural slices only.  
  Please cite the following paper if you use this dataset:

  Flanders AE, Prevedello LM, Shih G, *et al.*  
  *Construction of a Machine Learning Dataset Through Collaboration: The RSNA 2019 Brain CT Hemorrhage Challenge.*  
  **Radiology: Artificial Intelligence**, 2020; 2(3): e190211.  
  https://doi.org/10.1148/ryai.2020190211

---

- **BHSD (Brain Hemorrhage Segmentation Dataset, 2023)** — used for voxel-level evaluation.  
  For academic use, please cite:

  Wu, Biao, Xie, Yutong, Zhang, Zeyu, *et al.*  
  *BHSD: A 3D Multi-class Brain Hemorrhage Segmentation Dataset.*  
  In *International Workshop on Machine Learning in Medical Imaging (MLMI)*, pp. 147–156. Springer, 2023.

---

## 🧩 Repository Structure

```
WNet-Attention-ICH/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── src/
│   └── README.md
├── figures/
│   └── README.md
├── results/
│   └── README.md
└── data/
    └── README.md
```

---

## 📚 Citations

If you use this code, please cite:

- Flanders AE *et al.*, *Radiology: Artificial Intelligence*, 2020.  
  https://doi.org/10.1148/ryai.2020190211
- Wu B *et al.*, *MLMI Workshop (Springer)*, 2023.  
  https://bhsd-dataset.github.io

---

## 🪪 License
This project is licensed under the **MIT License** — see the LICENSE file for details.

---

## 🧠 Author
Developed by **Felipe Estay Serra**  
Biomedical Engineering Project — ICPRS 2025  
Millennium Institute for Intelligent Healthcare Engineering
