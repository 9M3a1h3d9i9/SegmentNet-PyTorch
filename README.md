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


pip install torch torchvision numpy matplotlib opencv-python pillow scikit-learn
🚀 Usage1. TrainingThe model is trained using a combination of Binary Cross Entropy (BCE) and Dice Loss.Optimizer: Adam (LR=0.0001) Batch Size: 8 Epochs: 300 (Paper recommendation) / 50 (Demo implementation)You can run the training notebook SegmentNet_Project.ipynb directly in Google Colab or on your local machine.2. Evaluation MetricsThe project evaluates the model using the following metrics:IoU (Intersection over Union)AccuracySensitivity (Recall)SpecificityF1-ScoreDice Coefficient📊 Results (BUSI Dataset)MetricPaper Reported This Implementation (Approx)IoU98.96%~90%Accuracy93.88%~94%F1-Score77.07%~80%(Note: The results in this repo depend on the number of epochs and random seed. The paper reported results are for the 3-class segmentation task.)🧩 Key Features Implemented[x] Custom DaM Block: Implements the Multi-focus Distance-aware Mechanism with linear complexity O(dSN).[x] Custom LFEB Block: Implements Depthwise Separable Convolutions with Smoothed ReLU.[x] Hybrid Loss Function: 0.5 * BCE + Dice Loss.[x] Automated Preprocessing: Handling multi-mask merging for BUSI dataset.🤝 ContributionThis project was implemented as part of a Master's degree coursework in Artificial Intelligence.Feel free to fork, open issues, or submit PRs.📜 CitationIf you use this code or the original paper logic, please cite the original authors:Code snippet@article{Ejiyi2024SegmentNet,
  title={A unified 2D medical image segmentation network (SegmentNet) through distance-awareness and local feature extraction},
  author={Ejiyi, Chukwuebuka Joseph and Qin, Zhen and et al.},
  journal={Biocybernetics and Biomedical Engineering},
  volume={44},
  pages={431--449},
  year={2024},
  publisher={Elsevier}
}
