# Model Evaluation & Overfitting Mitigation
**Hannah Johnson | M12 Assignment | Fashion-MNIST**

## Overview
This project demonstrates data splitting strategies and overfitting mitigation techniques applied to a CNN trained on the Fashion-MNIST dataset (10-class clothing image classification).

## Dataset
- **Fashion-MNIST** — 70,000 grayscale 28×28 images across 10 classes
- Split: 80% train / 20% validation from the original 60,000 training images; 10,000 held-out test images

## Techniques Applied
| Technique | Purpose |
|-----------|---------|
| Stratified train/val split | Preserve class balance across splits |
| L2 Regularization | Penalize large weights to reduce overfitting |
| Data Augmentation | Rotation, shift, flip to increase training diversity |
| Dropout (0.25 / 0.5) | Prevent neuron co-adaptation |
| Batch Normalization | Stabilize and accelerate training |
| Early Stopping | Halt training at peak validation performance |

## Results
| Model | Val Accuracy | Test Accuracy |
|-------|-------------|---------------|
| Baseline (no regularization) | 0.9059 | 0.9043 |
| Improved (all techniques) | 0.8652 | 0.8620 |

## Key Finding
The baseline model achieved slightly higher raw accuracy (90.4%) compared to the improved model (86.2%). This is expected — data augmentation intentionally makes training harder by exposing the model to distorted images, and early stopping halted training at epoch 7 of 50 before the regularized model could fully converge. The key benefit of the improved model is a much smaller gap between training and validation accuracy, indicating better generalization and less overfitting. Given more epochs or a tuned learning rate, the improved model would likely surpass the baseline.

## Files
- `model-evaluation-overfitting.ipynb` — Full notebook with baseline model, improved model, plots, and reflection
- `README.md` — This file

## How to Run
1. Clone the repository
2. Install dependencies: `pip install tensorflow scikit-learn matplotlib numpy`
3. Open and run `model-evaluation-overfitting.ipynb` top to bottom
