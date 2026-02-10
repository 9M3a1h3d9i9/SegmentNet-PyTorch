# SegmentNet-PyTorch

# SegmentNet: Unified 2D Medical Image Segmentation (PyTorch)

This repository contains a PyTorch implementation of **SegmentNet**, based on the paper *"A unified 2D medical image segmentation network (SegmentNet) through distance-awareness and local feature extraction"* published in Biocybernetics and Biomedical Engineering (2024).

This implementation focuses on the **Breast Ultrasound Images (BUSI)** dataset for tumor segmentation.

## 📄 Paper Overview
**Title:** A unified 2D medical image segmentation network (SegmentNet) through distance-awareness and local feature extraction  
**Authors:** Chukwuebuka Joseph Ejiyi et al.  
**Journal:** Biocybernetics and Biomedical Engineering  
**Link:** [Link to the paper if available, or DOI]

**SegmentNet** addresses the limitations of standard U-Net architectures by integrating two novel components:
1.  [cite_start]**Distance-aware Mechanisms (DaMs):** Captures global context and long-range dependencies between pixels[cite: 16, 20].
2.  [cite_start]**Local Feature Extractor Blocks (LFEBs):** Enhances the extraction of fine-grained local features using depthwise separable convolutions[cite: 16, 22].

## 🏗️ Architecture
The model is built upon a U-shape encoder-decoder architecture.
- **Encoder:** Incorporates DaMs to extract global context.
- **Bottleneck:** Utilizes LFEB to capture specific local image features.
- [cite_start]**Decoder:** Uses DaMs in skip connections to filter relevant features during upsampling[cite: 20, 292].

## 📂 Dataset
[cite_start]This implementation uses the **BUSI (Breast Ultrasound Images)** dataset[cite: 191].
- **Classes:** Normal, Benign, Malignant.
- **Preprocessing:** - Images resized to 256x256.
  - [cite_start]Multiple masks for a single image were merged as per the paper's instruction[cite: 196].
  - Data Augmentation (Random Rotation, Flip) applied.

## 🛠️ Installation & Requirements

To run this project, you need **Python 3.x** and the following libraries:

```bash
pip install torch torchvision numpy matplotlib opencv-python pillow scikit-learn
