#  Plant Disease Prediction Using CNN
A deep learning-based image classification project that uses a Convolutional Neural Network (CNN) to identify and classify plant diseases from leaf images.

## 📌 Overview

**Plant Disease Prediction Using CNN** is a deep learning and computer vision project designed to automatically identify plant diseases from leaf images.

The project uses a **Convolutional Neural Network (CNN)** to learn visual patterns from labeled plant leaf images and classify them into their respective disease categories.

Instead of manually examining every leaf, the trained model can analyze an uploaded image and provide a predicted disease class.

This project demonstrates the complete workflow of an image classification system, from **image preprocessing and model training to prediction and deployment using Docker**.

---

## 🎯 Problem Statement

Plant diseases can negatively affect crop health, agricultural productivity, and overall crop quality.

Traditional disease identification often requires manual inspection and agricultural expertise. An automated image-based system can assist in identifying diseases by analyzing visible patterns in plant leaves.

The objective of this project is to build a deep learning model that can:

* Accept a plant leaf image as input.
* Process and prepare the image for prediction.
* Automatically extract meaningful visual features.
* Classify the image into the appropriate disease category.
* Provide the predicted disease as the output.

---

## 💡 Solution

The project uses **Convolutional Neural Networks (CNNs)** because CNNs are well suited for image classification tasks.

The model learns hierarchical visual features from the training images.

For example:

```text
Image
  ↓
Edges
  ↓
Textures
  ↓
Shapes / Patterns
  ↓
Disease-specific Features
  ↓
Disease Classification
```

The early layers generally learn simple features such as edges and textures, while deeper layers learn more complex patterns useful for distinguishing between disease classes.

---

## 🔄 End-to-End Workflow

```text
                    Plant Leaf Dataset
                           ↓
                   Image Preprocessing
                           ↓
                 Resize & Normalization
                           ↓
                    Training Dataset
                           ↓
                     CNN Architecture
                           ↓
             ┌─────────────┴─────────────┐
             ↓                           ↓
       Convolution                  Activation
             ↓                           ↓
          Pooling                    ReLU
             └─────────────┬─────────────┘
                           ↓
                    Feature Extraction
                           ↓
                        Flatten
                           ↓
                 Fully Connected Layers
                           ↓
                    Output Layer
                           ↓
                  Disease Prediction
```

---

# 🧠 Convolutional Neural Network

CNN is a type of deep neural network commonly used for computer vision tasks.

The main components used in the project are:

### 1. Convolution Layer

The convolution layer applies filters/kernels to the input image to detect useful features.

For example, different filters can learn to detect:

* Edges
* Lines
* Textures
* Shapes
* Spots
* Patterns

The output of convolution is called a **feature map**.

---

### 2. ReLU Activation

The **Rectified Linear Unit (ReLU)** activation function introduces non-linearity into the neural network.

The function is:

```text
ReLU(x) = max(0, x)
```

It replaces negative values with zero while keeping positive values.

This helps the network learn complex patterns.

---

### 3. Pooling Layer

Pooling reduces the spatial dimensions of feature maps while retaining important information.

A common approach is **Max Pooling**.

For example:

```text
Large Feature Map
       ↓
Max Pooling
       ↓
Smaller Feature Map
```

Benefits include:

* Reduced computation
* Reduced number of parameters
* Helps retain important features
* Can help reduce overfitting

---

### 4. Flatten Layer

After the convolution and pooling operations, the feature maps are converted into a one-dimensional vector.

```text
Feature Maps
     ↓
Flatten
     ↓
1D Feature Vector
```

This vector is then passed to the fully connected layers.

---

### 5. Fully Connected Layers

The fully connected layers use the extracted features to determine the appropriate disease class.

They combine the learned features and perform the final classification.

---

### 6. Output Layer

The output layer produces the prediction for the different disease categories.

For a multi-class classification problem, the final layer can use **Softmax** to produce probabilities for each class.

Example:

```text
Healthy Leaf       → 0.08
Disease A          → 0.72
Disease B          → 0.15
Disease C          → 0.05
```

The class with the highest probability is selected as the predicted class.

---

# 🖼️ Image Preprocessing

Before feeding images into the CNN, the images need to be converted into a suitable format.

Typical preprocessing steps include:

### Image Resizing

Images may have different dimensions.

They are resized to a fixed size expected by the CNN.

```text
Original Image
      ↓
Resize
      ↓
Fixed Image Size
```

### Pixel Normalization

Pixel values generally range from:

```text
0 – 255
```

These values can be normalized to:

```text
0 – 1
```

This can help the neural network train more efficiently.

### Dataset Splitting

The dataset can be divided into:

* Training set
* Validation set
* Test set

The training data is used to learn model parameters.

The validation data is used to monitor model performance during training.

The test data is used to evaluate the final model on unseen images.

---

# 🏋️ Model Training

During training, the CNN receives batches of labeled leaf images.

The general training process is:

```text
Input Image
     ↓
Forward Propagation
     ↓
Prediction
     ↓
Calculate Loss
     ↓
Backpropagation
     ↓
Update Weights
     ↓
Next Batch
```

This process is repeated over multiple **epochs**.

### Loss Function

The loss function measures the difference between the actual class and the predicted class.

For multi-class classification, **categorical cross-entropy** or **sparse categorical cross-entropy** can be used depending on how the labels are represented.

### Optimizer

An optimizer updates the neural network's weights based on the calculated gradients.

Common optimizers include:

* Adam
* SGD
* RMSprop

---

# 📊 Model Evaluation

After training, the model can be evaluated using different metrics.

### Accuracy

Measures the percentage of correctly classified images.

```text
Accuracy =
Correct Predictions / Total Predictions
```

### Precision

Measures how many images predicted as a particular class actually belong to that class.

### Recall

Measures how many actual images belonging to a class were correctly identified.

### F1-Score

Combines precision and recall into a single metric.

### Confusion Matrix

A confusion matrix helps visualize which classes are being correctly classified and which classes are being confused with each other.

Example:

```text
                 Predicted
              A     B     C

Actual A     ✓     ✗     -
Actual B     -     ✓     ✗
Actual C     -     -     ✓
```

---

# 📈 Training and Validation Curves

Training and validation accuracy/loss can be plotted to understand the model's learning behavior.

For example:

```text
Epoch
  ↓
Training Accuracy ↑
Validation Accuracy ↑
```

If training accuracy continues increasing while validation accuracy stops improving or decreases, it may indicate **overfitting**.

Techniques such as:

* Data augmentation
* Dropout
* Regularization
* Early stopping
* Increasing dataset diversity

can be considered to improve generalization.

---

# 🔍 Prediction Pipeline

Once the CNN has been trained, a new leaf image can be passed to the model.

```text
New Leaf Image
      ↓
Resize
      ↓
Normalize
      ↓
CNN Model
      ↓
Feature Extraction
      ↓
Classification
      ↓
Class Probabilities
      ↓
Predicted Disease
```

Example output:

```text
Input:
Plant leaf image

Prediction:
Predicted Class: Disease A
Confidence: 92%
```

The exact output depends on the trained model and dataset.

---

# 🐳 Docker Deployment

Docker can be used to package the application and its dependencies into a container.

Instead of installing every dependency manually, the application can run inside a Docker container containing the required environment.

### Build Docker Image

```bash
docker build -t plant-disease-prediction .
```

### Run Docker Container

```bash
docker run -p 5000:5000 plant-disease-prediction
```

Docker helps provide a consistent environment across different systems.

---

# 🛠️ Technologies Used

| Technology         | Purpose              |
| ------------------ | -------------------- |
| Python             | Programming          |
| TensorFlow / Keras | Deep Learning        |
| CNN                | Image Classification |
| Computer Vision    | Image Analysis       |
| NumPy              | Numerical Operations |
| Pandas             | Data Handling        |
| Matplotlib         | Visualization        |
| Docker             | Containerization     |

---

# 📚 Key Concepts Demonstrated

This project demonstrates practical understanding of:

* Computer Vision
* Image Classification
* Convolutional Neural Networks
* Convolution
* Feature Maps
* Kernels / Filters
* ReLU Activation
* Pooling
* Flattening
* Fully Connected Layers
* Softmax Classification
* Image Preprocessing
* Image Normalization
* Dataset Splitting
* Model Training
* Forward Propagation
* Backpropagation
* Loss Functions
* Optimizers
* Epochs and Batches
* Model Evaluation
* Confusion Matrix
* Overfitting
* Docker Containerization

---

# 💻 Installation

Clone the repository:

```bash
git clone <your-github-repository-url>
```

Navigate to the project:

```bash
cd Plant-Disease-Prediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# 🚀 Running the Application

Run the application:

```bash
python app.py
```

Open the application in your browser and upload a plant leaf image.

The application processes the image and returns the predicted disease category.

---

# 🐳 Running with Docker

Build the Docker image:

```bash
docker build -t plant-disease-prediction .
```

Run the container:

```bash
docker run -p 5000:5000 plant-disease-prediction
```

---

# 🌾 Applications

The project can be used as a foundation for:

* Automated plant disease detection
* Smart agriculture systems
* Crop monitoring
* Agricultural image analysis
* Early disease identification
* Computer vision-based farming applications

---

# 🔮 Future Improvements

Possible improvements include:

* Implementing **transfer learning** using models such as ResNet, VGG, or EfficientNet.
* Applying data augmentation to improve model generalization.
* Increasing the diversity of training images.
* Adding confidence scores to predictions.
* Deploying the model on a cloud platform.
* Developing a mobile application.
* Adding disease treatment or prevention information.
* Supporting real-time camera-based plant disease detection.

---

# ⚠️ Limitations

The prediction quality depends on the quality and diversity of the training dataset.

Factors such as:

* Different lighting conditions
* Background variation
* Leaf orientation
* Image quality
* Unseen diseases
* Similar visual symptoms

can affect model performance.

Therefore, the model should be considered an **image-based classification system** rather than a replacement for professional agricultural diagnosis.

