# WNet-Attention-ICH

Official implementation of the paper  
**"Unsupervised Dual-Task W-Net with Spatial Attention for Intracranial Hemorrhage Detection and Segmentation"**  
Accepted at *IEEE ICPRS 2025*.

---

### 🩸 Overview
Unsupervised W-Net with spatial attention for epidural intracranial hemorrhage (EDH) detection and segmentation on non-contrast CT (NCCT).  
Pipeline: preprocessing → attention-based W-Net (Soft-N-Cut + 1-SSIM) → postprocessing.

---

### 📊 Datasets

- **RSNA Intracranial Hemorrhage Detection (2019)** — used for training with epidural slices only.  
  Please cite the following paper if you use this dataset:

  > Flanders AE, Prevedello LM, Shih G, *et al.*  
  > *Construction of a Machine Learning Dataset Through Collaboration: The RSNA 2019 Brain CT Hemorrhage Challenge.*  
  > **Radiology: Artificial Intelligence**, 2020; 2(3): e190211.  
  > [https://doi.org/10.1148/ryai.2020190211](https://doi.org/10.1148/ryai.2020190211)

---

- **BHSD (Brain Hemorrhage Segmentation Dataset, 2023)** — used for voxel-level evaluation.  
  For academic use, please cite:

  > Wu, Biao, Xie, Yutong, Zhang, Zeyu, *et al.*  
  > *BHSD: A 3D Multi-class Brain Hemorrhage Segmentation Dataset.*  
  > In *International Workshop on Machine Learning in Medical Imaging (MLMI)*, pp. 147–156. Springer, 2023.

  
### ⚙️ Quickstart
```bash
pip install -r requirements.txt
python src/train_unsupervised.py --data_dir /path/to/RSNA_EDH
python src/evaluate.py --test_dir /path/to/BHSD_EDH
