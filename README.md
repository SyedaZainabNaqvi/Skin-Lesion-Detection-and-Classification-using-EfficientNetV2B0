# Skin Lesion Detection and Classification using EfficientNetV2B0 COMPUTER VISION

This project presents an automated skin lesion detection and classification system using deep learning. The model classifies dermoscopic skin lesion images into multiple categories using the ISIC skin cancer dataset.

The main purpose of this project is to support computer-aided skin lesion analysis by combining image preprocessing, class balancing, and transfer learning.

## Project Overview

Skin lesion classification is a challenging medical image analysis task because different lesion types can look visually similar. Public datasets are also often imbalanced, which can reduce model performance on minority classes.

To address these challenges, this project uses a complete deep learning pipeline that includes preprocessing, class balancing, EfficientNetV2B0 transfer learning, and multi-metric evaluation.

## Dataset

The project uses the ISIC Skin Cancer Dataset from Kaggle. The dataset contains dermoscopic images from nine skin lesion classes.

## Methodology

The proposed pipeline includes the following stages:

1. Image preprocessing
2. Class balancing
3. EfficientNetV2B0 transfer learning
4. Model fine-tuning
5. Performance evaluation

## Image Preprocessing

The preprocessing pipeline includes:

* CLAHE contrast enhancement
* Median filtering for denoising
* Image resizing to 224 × 224 pixels
* Runtime preprocessing using a custom Keras sequence generator

CLAHE helps improve local contrast in dermoscopic images, while median filtering reduces noise while preserving important lesion edges.

## Class Balancing

The dataset contains class imbalance across different lesion categories. Random oversampling was applied to minority classes in the training set so that each class had balanced representation during training.

## Model Architecture

The classification model is based on EfficientNetV2B0 pre-trained on ImageNet-21K.

Training was completed in two stages:

### Stage 1: Head Training

The EfficientNetV2B0 backbone was frozen, and only the classification head was trained.

### Stage 2: Fine-Tuning

The top layers of the backbone were unfrozen and fine-tuned using a lower learning rate to improve model performance.

## Evaluation Metrics

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Cohen’s Kappa
* Confusion matrix
* Classification report
* AUC-ROC

## Results

Fine-tuning improved the model performance:

| Stage                  | Validation Accuracy | Validation Loss |
| ---------------------- | ------------------: | --------------: |
| Stage 1: Head Training |              81.85% |          0.6298 |
| Stage 2: Fine-Tuned    |              85.58% |          0.5294 |

The model performed well on several lesion classes, especially vascular lesions, but melanoma remained one of the most challenging classes due to visual similarity with benign lesions.

## Technologies Used

* Python
* TensorFlow
* Keras
* OpenCV
* scikit-learn
* scikit-image
* NumPy
* pandas
* Matplotlib
* KaggleHub

## Key Features

* Multi-class skin lesion classification
* EfficientNetV2B0 transfer learning
* CLAHE-based image enhancement
* Median filtering for denoising
* Random oversampling for class imbalance handling
* Two-stage training and fine-tuning
* Confusion matrix and class-wise performance analysis

## Future Work

Future improvements may include:

* Improving melanoma detection performance
* Integrating handcrafted texture features such as LBP and GLCM
* Testing on larger and more diverse clinical datasets
* Adding explainable AI techniques such as Grad-CAM
* Developing a real-time web or mobile application for skin lesion screening

## Authors

* Zainab
* Urooj Fatima

## Project Type

Computer Vision
Deep Learning
Medical Image Classification
