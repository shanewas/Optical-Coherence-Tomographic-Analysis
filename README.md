# Optical Coherence Tomographic Analysis

Deep learning research for Alzheimer's disease prediction using OCT retinal images.
Joint research with the University of Sydney (2018–2019).

Published: [IEEE — Alzheimer's Disease Prediction Using CNNs on OCT Images](https://ieeexplore.ieee.org/document/9306649)

## Overview

This project explores the use of Convolutional Neural Networks (CNNs) to predict
Alzheimer's disease from Optical Coherence Tomography (OCT) retinal scans.
We experimented with transfer learning approaches using VGG19 and Inception v3
pre-trained on ImageNet.

## Models

| Model | Approach | Notes |
|---|---|---|
| VGG19 | Transfer learning + fine-tuning | Best accuracy |
| Inception v3 | Transfer learning | Faster training |
| CNN Baseline | Trained from scratch | Lower accuracy, used as baseline |
| ResNet | Experiments | Comparative study |

## Results

- VGG19 achieved best classification accuracy on the OCT dataset
- Transfer learning significantly outperformed training from scratch
- findings contributed to the published IEEE paper (2019)

## Notebooks

| Notebook | Description |
|---|---|
| `data_preprocessing.ipynb` | Data cleaning and augmentation |
| `data_visualization.ipynb` | Dataset exploration and class distribution |
| `cnn_baseline.ipynb` | Baseline CNN model |
| `vgg19_training.ipynb` | VGG19 transfer learning |
| `vgg19_training_full.ipynb` | VGG19 full dataset training |
| `inception_v3_training.ipynb` | Inception v3 experiments |
| `resnet_experiments.ipynb` | ResNet comparative study |
| `cross_validation.ipynb` | K-fold cross validation |
| `model_evaluation.ipynb` | Final evaluation and metrics |
| `plot_results.ipynb` | Result visualization |

## Setup
```bash
git clone https://github.com/shanewas/Optical-Coherence-Tomographic-Analysis.git
cd Optical-Coherence-Tomographic-Analysis
pip install -r requirements.txt
jupyter notebook
```

## Citation

If you use this work, please cite:
> S. A. Nabil et al., "Alzheimer's Disease Prediction Using CNNs on OCT Images,"
> IEEE, 2019. https://ieeexplore.ieee.org/document/9306649

## Acknowledgements

Joint research with the University of Sydney.
Dataset: OCT retinal scan images.