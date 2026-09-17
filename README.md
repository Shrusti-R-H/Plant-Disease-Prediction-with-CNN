Plant Disease Prediction using CNN

A deep learning-based image classification project that uses a Convolutional Neural Network (CNN) to identify and classify plant diseases from leaf images.

📌 Project Overview

Plant diseases can significantly affect crop quality and production. Manually identifying diseases from plant leaves can be time-consuming and requires agricultural expertise.

This project uses Computer Vision and Deep Learning to automatically analyze leaf images and predict the corresponding plant disease.

The CNN model learns visual patterns such as edges, shapes, textures, and disease-specific features from the images and uses them to classify the input leaf into the appropriate disease category.

🎯 Objectives
Detect plant diseases from leaf images.
Apply image preprocessing techniques for deep learning.
Use CNN for automatic feature extraction and classification.
Train and evaluate an image classification model.
Create a deployable application using Docker.
🔄 Project Workflow
Leaf Image
    ↓
Image Preprocessing
    ↓
Image Resizing & Normalization
    ↓
CNN Model
    ↓
Convolution + ReLU
    ↓
Pooling
    ↓
Feature Extraction
    ↓
Fully Connected Layers
    ↓
Disease Classification
    ↓
Predicted Disease
🧠 CNN Architecture

The Convolutional Neural Network consists of the following major components:

1. Convolutional Layers

Extract important visual features from the input leaf images such as edges, patterns, and textures.

2. ReLU Activation

Introduces non-linearity into the network and helps the model learn complex patterns.

3. Pooling Layers

Reduce the spatial dimensions of feature maps while retaining important information.

4. Flatten Layer

Converts the extracted feature maps into a one-dimensional vector.

5. Fully Connected Layers

Use the extracted features to perform the final classification.

6. Output Layer

Produces the predicted plant disease class.

🛠️ Technologies Used
Python
Deep Learning
Convolutional Neural Network (CNN)
Computer Vision
TensorFlow / Keras
NumPy
Pandas
Matplotlib
Docker
