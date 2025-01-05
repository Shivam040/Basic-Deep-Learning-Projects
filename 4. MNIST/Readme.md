# MNIST Digit Classification

This project focuses on solving the MNIST digit classification problem using three distinct approaches:  
1. **[LeNet Architecture](#1-lenet-architecture)**  
2. **[Custom Architecture (Model 1)](#2-custom-architecture-model-1)**  
3. **[Custom Architecture (Model 2)](#3-custom-architecture-model-2)**  

## Dataset

The MNIST dataset contains 70,000 grayscale images of handwritten digits (0-9), where each image has a resolution of 28x28 pixels. The dataset is split into:  
- **Training Set**: 60,000 images  
- **Test Set**: 10,000 images  

## Approaches

### 1. LeNet Architecture
LeNet is a classic Convolutional Neural Network (CNN) architecture designed for handwritten character recognition.  
- **Architecture**:  
  - Convolutional Layers: Extract spatial features.  
  - Subsampling (Pooling): Reduces spatial dimensions.  
  - Fully Connected Layers: For classification.  
- **Activation Function**: ReLU  
- **Optimizer**: Stochastic Gradient Descent  
- **Loss Function**: Sparse Categorical Crossentropy  

### 2. Custom Architecture Model 1
This is a tailored CNN designed to explore alternative architecture designs.  
- **Features**:
  - First and Second Convolutional Layer: 16 filters, kernel size (3, 3), activation function ReLU.
  - First and Second MaxPooling Layer: Pool size (2, 2), reduces spatial dimensions after the first and Second convolution respectively.
  - Flatten Layer: Converts the 2D feature maps from the pooling layers into a 1D vector.
  - Fully Connected Layers:
    - Dense Layer: 64 neurons, activation function ReLU.
    - Output Layer: 10 neurons (one for each digit class), activation function Softmax for classification.
- **Optimizer**: Stochastic Gradient Descent
- **Loss Function**: Sparse Categorical Crossentropy  

### 3. Custom Architecture Model 2
A further optimized custom architecture incorporating insights from experimentation.  
- **Features**:  
  - Input Layer: Accepts images of shape (28, 28, 1) for grayscale MNIST digits. 
  - First Convolutional Layer:16 filters, kernel size (3, 3), activation function ReLU.
  - Second Convolutional Layer: 32 filters, kernel size (3, 3), activation function ReLU.
  - Third Convolutional Layer: 16 filters, kernel size (3, 3), activation function ReLU.
  - Subsampling (Pooling):
     - First MaxPooling Layer: Reduces spatial dimensions after the first convolution.
     - Second MaxPooling Layer: Further reduces spatial dimensions after the second convolution.
     - Third MaxPooling Layer: Further reduces spatial dimensions after the third convolution.
  -  Flatten Layer: Converts the 2D feature maps into a 1D vector for the fully connected layers.
  - Fully Connected Layers:
    - Dense Layer: 256 neurons, activation function ReLU.
    - Output Layer: 10 neurons (one for each digit class), activation function Softmax for classification.
- **Optimizer**: Stochastic Gradient Descent  
- **Loss Function**: Sparse Categorical Crossentropy 

## Results

| Model                   | Test Accuracy (%) | No. of epochs | Parameters     |  
|-------------------------|-------------------|-------------------------|----------------|  
| LeNet Architecture      | 97.61             | 15                      | ~44,426        |  
| Custom Architecture 1   | 88.88             | 15                      | ~28,794        |  
| Custom Architecture 2   | 97.84             | 15                      | ~16,346        |  

## Requirements

- Python 3.8+  
- TensorFlow 2.x  
- NumPy  
- Matplotlib
- Scikit-Learn 
