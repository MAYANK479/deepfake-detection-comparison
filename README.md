# Deepfake Detection Comparison

A deepfake image detection project comparing multiple deep learning models across two datasets using transfer learning and hybrid architectures.

## Overview

This project focuses on binary deepfake image classification using six different deep learning approaches. The main goal is to compare model performance on two datasets of different sizes and understand which architecture generalizes best for deepfake detection.

The models evaluated in this project are:

- VGG16 + MTCNN
- CNN
- LSTM
- CNN + LSTM
- CNN + InceptionV3
- CNN + InceptionV3 + Attention

The comparison is based on:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss

## Dataset Information

### Dataset 1
Small dataset used for initial model comparison.

- Real images: 1081
- Fake images: 960
- Total images: 2041

### Dataset 2
Large dataset used for broader performance evaluation.

- Total images: 10,000

## Models Used

### 1. VGG16 + MTCNN
A transfer learning model that uses MTCNN for face detection and VGG16 as the feature extractor for deepfake classification.

### 2. CNN
A custom convolutional neural network designed for binary classification of real and fake images.

### 3. LSTM
An LSTM-based model trained on reshaped image sequences to capture spatial patterns as sequential features.

### 4. CNN + LSTM
A hybrid architecture that combines convolutional feature extraction with sequential learning.

### 5. CNN + InceptionV3
A transfer learning model based on InceptionV3 for extracting richer visual features.

### 6. CNN + InceptionV3 + Attention
An improved version of the InceptionV3-based architecture with an attention mechanism to focus on more important facial regions.

## Performance Summary

### Dataset 1 Results

| Model | Accuracy | Loss | Val Accuracy | Val Loss |
|------|----------|------|--------------|----------|
| VGG16+MTCNN | 0.9647 | 0.1023 | 0.9924 | 0.0174 |
| CNN | 0.8251 | 0.3833 | 0.8838 | 0.2742 |
| LSTM | 0.5355 | 0.6858 | 0.5253 | 0.6971 |
| CNN+LSTM | 0.5566 | 0.6815 | 0.5707 | 0.6747 |
| CNN+InceptionV3 | 0.9520 | 0.1759 | 0.9924 | 0.0856 |
| CNN+InceptionV3+Attention | 0.9966 | 0.0265 | 1.0000 | 0.0077 |

### Dataset 2 Results

| Model | Accuracy | Loss | Val Accuracy | Val Loss |
|------|----------|------|--------------|----------|
| VGG16+MTCNN | 0.9690 | 0.0997 | 0.7275 | 1.1169 |
| CNN | 0.7030 | 0.6527 | 0.6475 | 0.7328 |
| LSTM | 0.5420 | 0.6861 | 0.5225 | 0.6880 |
| CNN+LSTM | 0.5370 | 0.6828 | 0.5200 | 0.7025 |
| CNN+InceptionV3 | 0.9890 | 0.0260 | 0.8425 | 0.7977 |
| CNN+InceptionV3+Attention | 0.9900 | 0.0346 | 0.8075 | 0.6593 |

## Accuracy Comparison

| Model | Dataset 1 Accuracy | Dataset 2 Accuracy |
|------|--------------------|--------------------|
| VGG16+MTCNN | 0.9647 | 0.9690 |
| CNN | 0.8251 | 0.7030 |
| LSTM | 0.5355 | 0.5420 |
| CNN+LSTM | 0.5566 | 0.5370 |
| CNN+InceptionV3 | 0.9520 | 0.9890 |
| CNN+InceptionV3+Attention | 0.9966 | 0.9900 |

## Graphs and Visual Comparisons

### Model Comparison Across Dataset 1 and Dataset 2

This graph compares all six models using training accuracy, validation accuracy, training loss, and validation loss.

![Model Comparison](images/model_comparison.png)

### Accuracy Comparison of All Models

This graph compares the overall training accuracy of all six models across both datasets.

![Accuracy Comparison](images/accuracy_comparison.png)

### Validation Accuracy Comparison

This graph highlights the validation accuracy of all models and helps compare their generalization performance.

![Validation Accuracy Comparison](images/validation_accuracy_comparison.png)

## Key Observations

- `CNN+InceptionV3+Attention` achieved the best overall performance on Dataset 1 with the highest training and validation accuracy and the lowest validation loss.
- `CNN+InceptionV3` and `VGG16+MTCNN` also showed strong results, especially on the smaller dataset.
- On Dataset 2, the transfer learning based models maintained very high training accuracy, but validation accuracy dropped compared to Dataset 1, suggesting some overfitting.
- `CNN`, `LSTM`, and `CNN+LSTM` performed significantly worse than the transfer learning models.
- LSTM-based approaches were less effective for this image classification task compared to CNN and Inception-based architectures.

## Project Structure

```bash
deepfake-detection-comparison/
│
├── .gitignore
├── Epics2.ipynb
├── epics1.ipynb
├── requirements.txt
└── images/
    ├── model_comparison.png
    ├── accuracy_comparison.png
    └── validation_accuracy_comparison.png

Installation
Clone the repository:

- git clone https://github.com/MAYANK479/deepfake-detection-comparison.git
cd deepfake-detection-comparison

Install dependencies:
- pip install -r requirements.txt

Usage

Open Jupyter Notebook:
- jupyter notebook

Then run:
- Epics2.ipynb

Future Improvements
- Add precision, recall, F1-score, and ROC-AUC comparisons
- Improve generalization using stronger data augmentation
- Convert notebooks into modular Python scripts
- Add model checkpoint tracking and experiment logging
- Deploy the best model in a web application

Author
Mayank Pandey