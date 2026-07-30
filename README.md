# 3D U-Net for Brain Tumour Segmentation on BraTS-GoAT 2024

This repository contains the Google Colab notebook I used to develop,
train, and evaluate a custom residual 3D U-Net with deep supervision for
multimodal brain MRI tumour segmentation.

## Results

The best model checkpoint was evaluated on an internal held-out
patient-level split of 203 cases.

| Region | Mean Dice |
|---|---:|
| Enhancing tumour | 0.7743 |
| Tumour core | 0.8443 |
| Whole tumour | 0.8813 |
| Mean | 0.8333 |

These results were obtained from an internal split of the available
BraTS-GoAT 2024 training data. They are not official challenge test-set
results or external clinical-validation results.

## My contribution

I implemented the multimodal MRI preprocessing, data augmentation,
model architecture, deep-supervision training workflow, and held-out
evaluation contained in the notebook.

Model development, training, and evaluation were performed in Google
Colab. I later adapted the trained model for local inference through a
Gradio interface in VS Code. This repository focuses on the original
model-development and evaluation workflow.

## Repository contents

- `brats_goat_2024_3d_unet_training_evaluation.ipynb`:
  Original Google Colab model-development, training, and evaluation
  workflow.
- `requirements.txt`:
  Main Python dependencies used in the experiment.

## Data availability

The BraTS-GoAT medical imaging dataset and trained model weights are not
included in this repository. Users must obtain authorised access to the
dataset and update the data paths in the notebook before execution.

## Limitations

- The reported results are based on an internal held-out split.
- The model has not been externally or prospectively validated.
- MRI volumes were resized to 128 × 128 × 128 for model training.
- This repository does not contain a clinical deployment system.

## Disclaimer

This is a research implementation and is not intended for clinical
diagnosis or patient management.
