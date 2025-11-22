# Hybrid Model for Image-to-Image Translation

## 🎓 M.Tech Research Project - Data Science & Analytics

This repository documents the research, methodology, and results of a Master's Thesis focused on enhancing **unpaired image-to-image translation** using Generative Adversarial Networks (GANs).

### 💡 Project Goal
To evaluate and implement an alternative generator architecture within the established **CycleGAN** framework, moving away from the traditional ResNet block and integrating the **U-Net** architecture to improve image quality and spatial consistency.

### 🔬 Methodology & Architecture

The research centered on a direct comparison between two CycleGAN variants:
1.  **Baseline:** CycleGAN with **ResNet** Generator.
2.  **Hybrid Model:** CycleGAN with **U-Net** Generator (inspired by its success in Pix2Pix for paired translation).

The implementation used the **Horse-to-Zebra** unpaired image dataset from Kaggle.

| Component | Standard | Hybrid (Our Approach) | Rationale |
| :--- | :--- | :--- | :--- |
| **Generator** | ResNet | **U-Net (Encoder-Decoder)** | U-Net's skip connections help preserve low-level spatial detail lost in deep ResNets, improving structural consistency. |
| **Framework** | CycleGAN | CycleGAN | Maintains the ability to train on unpaired data using **Cycle Consistency Loss**. |



### 📊 Key Results and Performance Metrics

The Hybrid (U-Net) model demonstrated significant performance improvements across structural, visual, and adversarial metrics, validating the hypothesis that U-Net is a better fit for high-quality image translation in this framework.

| Metric | ResNet (Baseline) | U-Net (Hybrid Model) | Goal | Improvement (%) |
| :--- | :--- | :--- | :--- | :--- |
| **FID Score** (Fréchet Inception Distance) | 72.4 | **65.8** | ↓ Lower is Better | **9.1%** |
| **SSIM** (Structural Similarity Index) | 0.61 | **0.72** | ↑ Higher is Better | **18.0%** |
| **PSNR (dB)** (Peak Signal-to-Noise Ratio) | 19.2 | **21.5** | ↑ Higher is Better | **12.0%** |
| **Cycle Consistency Loss** | 0.45 | **0.38** | ↓ Lower is Better | **15.5%** |

### 🛠️ Technical Stack
* **Deep Learning Framework:** Python, PyTorch/TensorFlow (implementation details in the notebook)
* **GAN Architecture:** CycleGAN, U-Net, ResNet
* **Computer Vision:** Image Processing, Unpaired Image Translation
* **Dataset:** Horse-to-Zebra (Kaggle)

### 📓 Code and Documentation
The full implementation, including data loading, model definition, training loops, and visual comparisons, is available in the attached Jupyter Notebook.

* **Jupyter Notebook:** `Project I2I.ipynb`
    * *Note: This notebook is configured for use in Google Colab and focuses on the model architecture and training process.*

### ⚠️ Intellectual Property Disclaimer
This research was conducted as part of the requirements for the Master of Technology in Data Science and Analytics at **MIT World Peace University, Pune**.

The official thesis document, which contains university logos, seals, and confidential academic information, remains the property of the University and is **not** available in this public repository. This README serves only as a technical summary of the public-facing methodology and results.
