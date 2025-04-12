# Artifact Detection Model

## Description
This repository contains a solution for detecting artifacts in generated images using a deep learning approach with ResNet18. 
When I made EDA, I have noticed thar data distribution is 1:9 class 1 and class 0 respectfully.

The model addresses a binary classification task (artifact vs. artifact-free) with a significant class imbalance (1:9). Augmentation techniques are applied to the minority class to improve performance.

## Installation
1. Download files.
2. Install dependencies: `!pip install -r requirements.txt`.
3. Mount Google Drive and update `train_dir` and `test_dir` in Cell 2 with your dataset paths.
4. Ensure a GPU is enabled: `Runtime` > `Change runtime type` > Select `GPU`(if you are working in Colab or Kaggle).

## Usage
1. Run all cells sequentially (in Google Colab).
2. The model trains for 10 epochs, saves the best model based on validation micro F1 score, and performs inference on the test set.
3. Output includes accuracy, micro F1 score, and class-wise metrics (precision, recall, F1).

## Final Metrics
- **Micro F1 Score**: 0.9950 (based on 99.50% accuracy and balanced performance).
- **Accuracy**: 99.50% (199/200 correct).
- **Class 0 (Artifacts)**: Precision 1.00, Recall 0.95, F1 0.97.
- **Class 1 (No Artifacts)**: Precision 0.99, Recall 1.00, F1 1.00.
- ![Screenshot from 2025-04-12 17-29-56](https://github.com/user-attachments/assets/2806125f-04c1-47cd-b088-e2c28807bbcd)
- ![image](https://github.com/user-attachments/assets/f4131b1d-dcf9-4bbf-845c-21aa5555750e)



- The solution leverages Colab's free GPU.
- Augmentation (flips, jitter, rotation) for class 0 improved minority class detection.
- [Advanced] Ensemble approaches (e.g., ResNet + Vision Transformer) could be explored for further improvement.
