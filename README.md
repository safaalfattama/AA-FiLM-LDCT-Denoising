# AA-FiLM-LDCT-Denoising

Official PyTorch implementation of:

**“Anatomically Adaptive Feature-wise Linear Modulation for Deep Learning-Based Low-Dose CT Denoising”**

---

## 📌 Overview

Low-dose CT (LDCT) images exhibit **region-dependent noise**, where noise characteristics vary across anatomical structures such as lung, soft tissue, and bone.

This repository introduces **AA-FiLM**, a hybrid framework that combines:

* **Global FiLM (GFiLM)** → models global noise statistics
* **Local FiLM (LFiLM)** → performs region-aware feature modulation

The method enables **anatomically adaptive denoising** by conditioning feature transformations on both global and local information.

---

## 🧠 Key Contributions

* Anatomically adaptive feature modulation using region priors
* Hybrid FiLM design (global + local)
* Physically interpretable architecture aligned with CT noise properties
* End-to-end LDCT denoising framework

---

## 🏗️ Repository Structure

```
AA-FiLM-LDCT-Denoising/
│
├── dataset.py        # Dataset loading and preprocessing
├── model.py          # AA-FiLM architecture
├── training.py       # Training pipeline
├── testing.py        # Testing and evaluation
├── README.md
```

---

## 📂 Dataset

The dataset should be organized as:

```
root_dir/
│
├── Patient_001/
│   ├── quarter_1mm/   # LDCT (low-dose)
│   ├── full_1mm/      # NDCT (full-dose)
│
├── Patient_002/
│   ├── quarter_1mm/
│   ├── full_1mm/
```

Each folder contains DICOM files (`.IMA`).

---


## 🧩 Model

The proposed architecture is a **Hybrid U-Net with FiLM modulation**:

* Encoder → Global FiLM (GFiLM)
* Decoder → Local FiLM (LFiLM)

---

## ⚙️ Installation

```bash
git clone https://github.com/safaalfattama/AA-FiLM-LDCT-Denoising.git
cd AA-FiLM-LDCT-Denoising
```

---

## 📦 Requirements

```
torch
numpy
opencv-python
pydicom
scikit-image
matplotlib
tqdm
pytorch-msssim
```

---

## 🚀 Training

```bash
python training.py
```

Training details:

* Loss: L1 + SSIM
* Optimizer: Adam
* Learning rate: 1e-4
* Scheduler: cosine annealing

---

## 🧪 Testing

```bash
python testing.py
```

Outputs:

* Denoised images
* PSNR / SSIM / MSE metrics
* Visualization results

---

## 📊 Results

The model improves:

* Noise suppression
* Structural preservation
* Quantitative metrics (PSNR, SSIM)

---



## 🔁 Reproducibility

To reproduce results:

1. Prepare dataset as described
2. Train using `training.py`
3. Evaluate using `testing.py`

---


## 📧 Contact

For questions:

**Safa Alfattama**  
Email: alfattamasafa@gmail.com
