# Satellite Imagery Super-Resolution using GAN (SRGAN)

This project focuses on enhancing the resolution of satellite images using a deep learning-based Super-Resolution Generative Adversarial Network (SRGAN). It addresses the limitations of low-resolution satellite data by reconstructing high-resolution outputs using adversarial and perceptual learning.


---

## 🧠 Abstract

Due to limitations in satellite sensors and acquisition costs, high-resolution satellite imagery is scarce. This project leverages SRGAN, a GAN-based model, to upscale low-resolution images by a factor of 4. Trained on 83,000+ patch pairs from the DOTA-v1.0 dataset, the generator learns perceptual and structural features, while the discriminator ensures photo-realistic outputs.

---

## 📁 Dataset

- **DOTA-v1.0** (Dataset for Object Detection in Aerial Images)
- 469 high-resolution images used
- 83,000+ HR-LR patch pairs extracted using a sliding window (256x256 HR, 64x64 LR)

---

## 🏗️ Methodology

- **Generator**: 16 Residual Blocks, PixelShuffle Upsampling (×2 layers), Final Conv (9×9)
- **Discriminator**: 8 Convolutional Blocks + Adaptive Average Pooling + Dense Layers
- **Loss Functions**:
  - Content Loss (MSE)
  - Adversarial Loss (Binary Cross-Entropy)
  - Perceptual Loss (VGG19 relu5_4)
- **Optimizers**:
  - Adam (lr = 5e-5, β1 = 0.9, β2 = 0.999)

---

## ⚙️ Training Setup

- Platform: **Kaggle Notebooks**
- Hardware: **2 × NVIDIA Tesla T4 GPUs**
- Epochs: **50**
- Batch Size: **16**
- Training Time: **90–105 minutes per epoch**

---

## 📉 Training Plots

### 🔁 Generator & Discriminator Loss over Epochs

<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/a261aef4-8147-4f0b-a96e-acbe484c92ec" />


- Generator Loss decreased steadily, ensuring stable learning.
- Discriminator Loss fluctuated as expected due to adversarial feedback.

### 📈 PSNR & SSIM over Epochs

<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/95410dcf-0ade-4546-a567-0eff21e916f7" />


- Peak PSNR: **24.62 dB**
- Max SSIM: **0.6932**

---

## 🔍 Testing Results

Two different test sets were evaluated:

| Test Set Description             | PSNR   | SSIM   |
|----------------------------------|--------|--------|
| Seen Images (40 samples)         | 26.45  | 0.7101 |
| Unseen Images (30 samples)       | 25.39  | 0.6884 |

---

## 📊 Sample Outputs

<img width="1108" height="370" alt="3" src="https://github.com/user-attachments/assets/eff77b73-918d-4eae-a5ce-311750caaa7b" />

<img width="1112" height="417" alt="4" src="https://github.com/user-attachments/assets/ae69e78e-73c4-4e67-b919-581aa94442e0" />


---

## 📏 Evaluation Metrics

- **PSNR (Peak Signal-to-Noise Ratio)**: Measures pixel-level accuracy.
- **SSIM (Structural Similarity Index)**: Measures perceived visual similarity.

---

## 🧪 Key Takeaways

- SRGAN shows strong generalization even on unseen test data.
- Perceptual quality improved dramatically compared to traditional upscaling.
- Suitable for real-world applications in surveillance, agriculture, and urban mapping.

---

## 📚 References

1. Lavreniuk et al. - *GANs for Satellite Super-Resolution using Transformers* (IEEE 2024)  
2. Abhishek Pandey et al. - *DiffIR vs SRGAN Comparison* (AJCT 2024)  
3. Ran Li et al. - *Super-Resolution for Single Satellite Image* (ISPRS 2022)  
4. Mahee Tayba et al. - *SRGAN for MODIS Imagery* (CSCI 2021)  
5. Zhongyuan Wang et al. - *Ultra-dense GAN for Satellite SR* (Neurocomputing 2020)  
6. Rajamohana et al. - *SRGAN vs ESRGAN for INSAT Imagery* (JSIR 2024)  
7. Xiangyu Xue et al. - *R-SRGAN with Wasserstein Loss* (IEEE ICAIBD 2020)  

---

## 📬 Contact

For questions or contributions, feel free to open an issue or contact the project team.

---

## 📌 Team Members

- A. Venkata Satya
- K. N. Lakshmi 
- K. Hemavardhan Reddy 
- K. V. Vamshidhar Reddy 


