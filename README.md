# Optical Coherence Tomographic Analysis

**Alzheimer's disease prediction from OCT retinal images using transfer learning on VGG19 and Inception v3.**

Joint research with University of Sydney (2018–2019). Published at IEEE EMBC 2019.

> S. A. Nabil et al., "Alzheimer's Disease Prediction Using CNNs on OCT Images," IEEE, 2019.
> https://ieeexplore.ieee.org/document/9306649

## What this project does

```
Raw OCT retinal scans (64-bit float TIFF images)
↓
Data preprocessing — normalization, augmentation, class balancing
↓
Transfer learning — VGG19 / Inception v3 / ResNet pretrained on ImageNet
↓
Fine-tuning on OCT dataset for binary Alzheimer's classification
↓
Model evaluation — accuracy, sensitivity, specificity, ROC-AUC
```

## The pipeline (what I personally did)

1. **Data preprocessing** — wrote `data_preprocessing.ipynb` to handle TIFF image loading, intensity normalization across different scanner devices, and data augmentation (rotation, flip, brightness) to expand the limited dataset
2. **Model experiments** — ran VGG19 and Inception v3 transfer learning with `vgg19_training.ipynb` and `inception_v3_training.ipynb`. Compared against a from-scratch CNN baseline
3. **Cross-validation** — implemented K-fold cross validation (`cross_validation.ipynb`) to ensure model generalization wasn't inflated by train-test leakage
4. **Evaluation** — final metrics in `model_evaluation.ipynb`

**Key finding:** Transfer learning from ImageNet significantly outperformed training from scratch. VGG19 achieved the best accuracy in the comparative study.

## Project structure

```
Optical-Coherence-Tomographic-Analysis/
├── data_preprocessing.ipynb      # Data cleaning, TIFF loading, normalization, augmentation
├── data_visualization.ipynb       # Class distribution, image sample inspection
├── cnn_baseline.ipynb             # From-scratch CNN baseline for comparison
├── vgg19_training.ipynb          # VGG19 transfer learning + fine-tuning
├── vgg19_training_full.ipynb     # VGG19 on full dataset
├── inception_v3_training.ipynb    # Inception v3 transfer learning
├── resnet_experiments.ipynb       # ResNet comparative study
├── cross_validation.ipynb         # K-fold cross validation
├── model_evaluation.ipynb          # Final accuracy, sensitivity, specificity, ROC
├── plot_results.ipynb             # Visualization of results
└── requirements.txt
```

## Tech stack

- **Python 3** — core language
- **TensorFlow / Keras** — CNN model training
- **scikit-learn** — cross-validation, metrics, ROC-AUC
- **pandas + numpy** — data handling
- **OpenCV / PIL** — image preprocessing
- **Jupyter** — all experiments

## Results

| Model | Approach | Outcome |
|---|---|---|
| VGG19 | Transfer learning + fine-tuning | Best accuracy in comparative study |
| Inception v3 | Transfer learning | Faster training, comparable accuracy |
| CNN Baseline | From scratch | Lower accuracy — used as baseline |
| ResNet | Comparative | Used for ablation comparison |

Transfer learning consistently outperformed training from scratch on this dataset size.

## Dataset

The OCT images used in this study were collected from a clinical setting. Due to patient privacy requirements, the raw dataset cannot be publicly released. Sample preprocessed outputs and class distribution statistics are shown in `data_visualization.ipynb`.

If you have access to a similar OCT dataset (e.g., OCT眼底画像 from UCI or similar), the pipeline in `data_preprocessing.ipynb` can be adapted directly.

## How to reproduce

```bash
git clone https://github.com/shanewas/Optical-Coherence-Tomographic-Analysis.git
cd Optical-Coherence-Tomographic-Analysis
pip install -r requirements.txt
jupyter notebook
```

Open `vgg19_training.ipynb` to follow the training pipeline from data loading through to model evaluation.

## What this shows for AI/ML roles

- End-to-end ML pipeline experience (data → preprocessing → model → evaluation)
- Transfer learning methodology — not just running a tutorial, understanding why it works
- Experimental discipline (cross-validation, ablation studies)
- Publication-level research execution (IEEE peer review)
- Healthcare/medical imaging domain experience

## Citation

If this work is useful to you, cite:
```bibtex
@inproceedings{Nabil2019Alzheimer,
  author={Nabil, S. A. and others},
  title={Alzheimer's Disease Prediction Using CNNs on OCT Images},
  booktitle={IEEE EMBC},
  year={2019},
  url={https://ieeexplore.ieee.org/document/9306649}
}
```