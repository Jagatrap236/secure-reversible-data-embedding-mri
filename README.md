# Secure and Reversible Data Embedding in Medical Images Using U-Net Segmentation and XOR Encryption

A secure and reversible data embedding framework for brain tumor MRI images that integrates U-Net-based tumor segmentation, LSB-based reversible data hiding, and XOR encryption for transmission security.

> **B.Tech Final Year Project (4-2 Semester)**
> Department of CSE, Vignan's Foundation for Science, Technology and Research (VFSTR), Guntur, Andhra Pradesh

## Authors

- **J. Dayanika** — jdayanika@gmail.com
- **P. Jagatrayee** — jagatrayeepotti@gmail.com
- **A. Mary Kavya** — kavya060605@gmail.com

## Overview

The rapid growth of digital healthcare systems demands secure storage and transmission of medical images without compromising diagnostic quality. This project presents a framework that:

1. **Denoises** MRI images using Non-Local Means (NLM) filtering
2. **Segments** tumor regions using U-Net architecture
3. **Embeds** patient data within the tumor ROI using LSB steganography
4. **Encrypts** the stego image using XOR encryption
5. **Restores** the original image losslessly after data extraction

Reversibility is guaranteed by storing original pixel LSBs before embedding and reapplying them during restoration, yielding **zero reconstruction error**.

## Pipeline

```
MRI Input → Preprocessing → Noise Estimation → NLM Denoising
    → Grayscale Verification → U-Net Tumor Segmentation
    → LSB Embedding (in tumor ROI) → XOR Encryption
    → Base64 Encoding → Transmission
    → Decryption → Data Extraction → Image Restoration
```

## Results

| Metric | Stego Stage | Restoration Stage |
|--------|------------|-------------------|
| PSNR | 73.83 dB | ∞ (perfect) |
| SSIM | 0.99999 | 1.0 |
| MSE | 0.00269 | 0.0 |

### Comparison with Existing Methods

| Method | PSNR (dB) | SSIM | MSE |
|--------|-----------|------|-----|
| Interp.+PEE (2025) | 44.21 | 0.982 | 1.23 |
| Blockchain RDH (2021) | 41.35 | 0.965 | 2.85 |
| U-Net Steg. (2019) | 38.72 | 0.941 | 6.45 |
| Edge+DE (2018) | 46.18 | 0.988 | 0.98 |
| Hist. Modif. (2020) | 48.56 | 0.991 | 0.72 |
| ROI-RDH (2015) | 43.67 | 0.979 | 1.56 |
| Sec. RDH+Enc. (2020) | 40.92 | 0.958 | 3.12 |
| BM3D Denoise (2024) | 36.45 | 0.912 | 8.75 |
| DL Steg. Review (2023) | 39.88 | 0.952 | 4.96 |
| **Proposed Method** | **73.83** | **0.99999** | **0.00269** |

## Dataset

This project uses the **BraTS 2020** (Brain Tumor Segmentation) dataset.

**Download:** [Kaggle — BraTS 2020 Training & Validation](https://www.kaggle.com/datasets/awsaf49/brats20-dataset-training-validation)

> **Note:** The dataset is not included in this repository due to its size. Please download it separately and update the data path in the notebook.

## Setup & Installation

### Prerequisites

- Python 3.8+
- [Google Colab](https://colab.research.google.com/) (recommended) or a local Jupyter environment

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Running the Notebook

1. Download the BraTS 2020 dataset from the [Kaggle link](https://www.kaggle.com/datasets/awsaf49/brats20-dataset-training-validation) above
2. Extract the dataset to a local directory
3. Open `secure_reversible_data_embedding_mri.ipynb` in Jupyter or Google Colab
4. Update the `DATA_DIR` variable in the first code cell to point to your extracted dataset
5. Run all cells sequentially

## Tech Stack

- **Python** — Core language
- **NumPy** / **OpenCV** — Image processing and array operations
- **Matplotlib** — Visualization
- **NiBabel** — NIfTI medical image format I/O
- **TensorFlow / Keras** — U-Net segmentation model

## Project Report

The full IEEE-format research paper is available at [`Project_Report.pdf`](./Project_Report.pdf).

## Repository Structure

```
secure-reversible-data-embedding-mri/
├── secure_reversible_data_embedding_mri.ipynb   # Main notebook
├── Project_Report.pdf                            # IEEE-format paper
├── README.md                                     # This file
├── requirements.txt                              # Python dependencies
├── LICENSE                                       # MIT License
└── .gitignore                                    # Git ignore rules
```

## Keywords

MRI, Reversible Data Hiding (RDH), Medical Image Security, U-Net, Image Encryption, Image Restoration, Convolutional Neural Networks (CNN), LSB Embedding, BraTS 2020

## License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.
