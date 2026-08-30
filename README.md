
# Explainable Multiclass Retinal Disease Classification

An explainable deep learning system for multiclass retinal fundus image classification, combining deep visual representations with handcrafted clinical image features to improve classification performance and model interpretability.

## Overview

This project develops a computer vision pipeline for classifying retinal fundus images into four categories:

- **Normal**
- **Myopia**
- **Retinitis Pigmentosa (RP)**
- **Hypertensive Retinopathy (HR)**

The system combines deep features learned from a ResNet-18 model with handcrafted retinal image features. The fused representation is then classified using a Fully Connected Neural Network (FCNN).

The project also incorporates explainability techniques to visualize which regions of retinal images contribute to model predictions.

## Model Architecture

The overall pipeline is:

*Retinal Fundus Image*
↓
*Image Preprocessing*
↓
*ResNet-18 Feature Extraction*
+
*Handcrafted Clinical Features*
↓
*Feature Fusion*
↓
*FCNN Classifier*
↓
*Multiclass Prediction*

### Deep Features

A **ResNet-18** convolutional neural network is used to learn high-level visual representations from retinal fundus images.

### Handcrafted Features

Additional image-based features are extracted to provide complementary information, including features related to:

- Vessel density
- Fractal dimension
- Image entropy
- Foveal avascular zone (FAZ) characteristics
- Optic disc measurements
- Color statistics

### Feature Fusion

The deep features extracted from ResNet-18 are combined with the handcrafted retinal features.

The fused representation is provided to an FCNN classifier for final multiclass prediction.

## Explainability

To improve interpretability, the project uses:

- **Grad-CAM++**
- **Saliency maps**

These methods generate visual explanations showing regions of the retinal image that contributed to the model's prediction.

The `explainability/` directory contains generated visual explanations and Grad-CAM++ results.

## Results

| Model | Test Accuracy |
|---|---:|
| ResNet-18 | **88.75%** |
| Fused Features + FCNN | **91.82%** |

The fused model demonstrates improved classification performance compared with using the deep representation alone.

## Dataset

The project uses a retinal fundus image dataset containing approximately **15,000 images** across four disease categories.

The dataset is not included directly in the standard repository files because of its large size.

## Repository Structure

```text
RetinalFundus/
│
├── RESNET.ipynb
├── features.ipynb
├── final pipeline.ipynb
├── last fusion a+b.ipynb
│
├── features_final_all_fast.csv
├── fundus_embeddings.csv
├── merged_fundus_features.csv
├── modelBFinalodfeat.csv
├── explain_with_names.xlsx
│
├── explainability/
│   ├── Grad-CAM++ visualizations
│   └── model explanation outputs
│
├── fundus_training_runs/
│   ├── model training results
│   ├── evaluation metrics
│   ├── confusion matrices
│   └── training artifacts
│
├── models-20260830T091120Z-1-001.zip
│
├── .gitattributes
└── .gitignore
````

## Technologies

* Python
* PyTorch
* ResNet-18
* Fully Connected Neural Networks (FCNN)
* Computer Vision
* Deep Learning
* OpenCV
* NumPy
* Pandas
* Scikit-learn
* Grad-CAM++
* Git / Git LFS
* Jupyter Notebook

## Application / Demo

An interactive interface for the retinal fundus classification system is available on Hugging Face:

*[Live Demo](https://huggingface.co/spaces/Azkiya/fundus_image_classification)*

The interface provides a practical demonstration of the retinal image classification workflow.

> Note: The Hugging Face Space may sleep when inactive and may need to be restarted before use.

## Research Focus

This project focuses on:

* Computer vision for medical image analysis
* Multiclass retinal disease classification
* Deep feature extraction
* Handcrafted feature engineering
* Feature-level fusion
* Explainable AI
* Model evaluation
* Translating research models into practical applications

## Future Improvements

Potential future work includes:

* Testing additional state-of-the-art vision architectures
* Improving class imbalance handling
* Cross-dataset evaluation
* Model calibration and uncertainty estimation
* Inference optimization
* Deployment optimization
* Further investigation of explainability methods

## Authors

Hafsa Ayub & Azkiya Manal

BSc Bioinformatics
COMSATS University Islamabad

---

### Project Demo

🔗 *Hugging Face:* [https://huggingface.co/spaces/Azkiya/fundus_image_classification](https://huggingface.co/spaces/Azkiya/fundus_image_classification)

