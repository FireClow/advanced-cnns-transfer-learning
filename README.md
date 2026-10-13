# Advanced CNNs and Transfer Learning

## Project Overview

This project explores Convolutional Neural Networks (CNNs) and transfer learning for image classification using a subset of the Oxford-IIIT Pet dataset. The experiments compare training a CNN from scratch, feature extraction using pretrained models, fine-tuning, and the effect of data augmentation.

The project was developed as part of the Advanced CNNs and Transfer Learning assignment.

## Dataset

The experiments use a subset of the Oxford-IIIT Pet dataset containing 10 classes and 996 images.

Dataset split:
- Training: 697 images
- Validation: 149 images
- Testing: 150 images

Image preprocessing and experimental settings:
- Image size: 224 × 224 pixels
- Normalization: ImageNet mean and standard deviation
- Batch size: 32
- Random seed: 42
- Loss function: Cross-Entropy Loss
- Optimizer: AdamW
- Early stopping patience: 3 epochs

The dataset is divided into training, validation, and test sets to evaluate model performance.

## Experiments

The project contains the following experiments:

- **B1 — ResNet18 from Scratch:** Trains ResNet18 without pretrained weights.
- **B2 — Feature Extraction:** Uses pretrained ResNet18 as a feature extractor and trains the classification head.
- **B3 — Fine-Tuning:** Fine-tunes the ResNet18 `layer4` and classification head.
- **B4 — Data Augmentation Comparison:** Compares feature extraction with and without data augmentation.
- **B5 — EfficientNet-B0:** Additional experiment using pretrained EfficientNet-B0 for feature extraction.

## Installation

Python 3 and pip are required. It is recommended to use a virtual environment.

```bash
python -m venv .venv
source .venv/bin/activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

If PyTorch installation fails, install the appropriate version for your operating system and hardware using the official PyTorch installation instructions.

## Running the Experiments

1. Clone this repository:

   ```bash
   git clone <YOUR_GITHUB_REPOSITORY_URL>
   cd advanced-cnns-transfer-learning
   ```

2. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

3. Open the project's `.ipynb` notebook.
4. Run the cells in order to load the dataset, preprocess images, train the models, and evaluate the results.

Dataset paths and download settings may need to be adjusted depending on the environment.

## Results Summary

The following table summarizes the main experimental results.

| Experiment | Validation Accuracy | Test Accuracy | Test Macro F1 |
|---|---:|---:|---:|
| B1 — ResNet18 from Scratch | 46.98% | 37.33% | 37.21% |
| B2 — Feature Extraction | 92.62% | 90.67% | 90.61% |
| B3 — Fine-Tuning | 93.29% | 92.00% | 91.93% |
| B4 — Without Augmentation | 90.60% | 92.67% | 92.62% |
| B5 — EfficientNet-B0 | 93.29% | 90.00% | 90.08% |

The results show that pretrained models substantially outperform training ResNet18 from scratch on this relatively small dataset. Fine-tuning achieves a strong balance between validation accuracy and test performance. The experiment without data augmentation also achieves competitive test results, although the comparison should be interpreted in the context of the dataset split and training configuration.

## Project Structure

The repository may contain the following files:

```text
advanced-cnns-transfer-learning/
├── README.md
├── requirements.txt
├── *.ipynb
├── *.csv
├── *.json
└── *.png
```

The notebook contains the implementation and experiment outputs. CSV and JSON files can be used to store metric logs, while PNG files can contain generated plots.

## Limitations

- The dataset contains only 996 images from 10 classes.
- Results may vary with different random seeds, data splits, and hardware.
- The experiments use a limited set of architectures and hyperparameters.
- High accuracy on this subset does not guarantee equivalent performance on other datasets.

## Academic Integrity and AI Disclosure

AI assistance was used to support parts of the documentation and development workflow. The experiments and reported metrics should be checked against the executed notebook and corresponding output files.


