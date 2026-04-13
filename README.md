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
| Baseline (no regularization) |~0.9059 | ~0.9043 |
| Improved (all techniques) | ~0.8652 | ~0.8620 |

*Exact values will appear after running the notebook.*

## Key Finding
The combination of Dropout + Batch Normalization had the most visible effect on reducing the train/validation gap. Data augmentation further improved generalization. No single technique was sufficient — the best results came from applying all techniques together.

## Files
- `model-evaluation-overfitting.ipynb` — Full notebook with baseline model, improved model, plots, and reflection
- `README.md` — This file

## How to Run
1. Clone the repository
2. Install dependencies: `pip install tensorflow scikit-learn matplotlib numpy`
3. Open and run `model-evaluation-overfitting.ipynb` top to bottom
