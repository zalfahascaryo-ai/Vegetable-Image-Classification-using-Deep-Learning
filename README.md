# Vegetable Image Classification using Deep Learning
## 🔎 Project Overview
This project focuses on classifying different types of vegetables using deep learning techniques. By leveraging image data, the model learns visual patterns such as shape, color, and texture to accurately identify vegetable categories using a simple deep learning approach.

This project demonstrates an end-to-end pipeline, including data preprocessing, model development, evaluation, and inference.

## ⚙️ Project Pipeline
### 1. Data Collection:
* The dataset consists of labeled vegetable images collected from Kaggle:
  > https://www.kaggle.com/datasets/misrakahmed/vegetable-image-dataset
* The dataset contains 15 classes of vegetables
* Images are organized into a DataFrame for easier preprocessing and model development

### 2. Data Preprocessing
* Split Data: Although the dataset originally provides a `70:15:15` split, the data is re-split manually from the training set into `80:10:10` for better control
* Data Augmentation (Training Set):
  - Rescale = 1./255
  - Rotation range = 15
  - Width shift range = 0.2
  - Height shift range = 0.3
  - Zoom range = 0.3
  - Brightness range = 0.7 - 1.3
  - Shear range = 0.2
  - Horizontal flip
  - fill mode = nearest

  This augmentation generates approximately 375 new images, resulting in a total of around 1575 training images
* Validation & Test Data: Only rescaling (1./255) is applied to maintain data authenticity. Each class generates around 47 images, with a total of approximately 1547 images for validation and testing

### 3. Model Building
* The model is built using a Sequential CNN architecture
* It consists of:
  - 4 Convolutional layers
  - Pooling layers
  - Fully connected (Dense) layers
* Optimizer: Adam
* Callback used:
  - Early stopping when training and validation accuracy exceed 95%
  - Reduce learning rate on plateau
  - Model checkpoint to save the best-performing model

This architecture is chosen to understand the fundamental concepts of deep learning before moving to more advanced approaches.

### 4. Model Evaluation
The model is evaluated using:
* Confusion Matrix (to analyze class-wise performance)
* Test Dataset Evaluation
* Training History Plots (accuracy & loss curves)

### 5. Convert model 
The trained model is converted into multiple formats:
* .keras: Native keras format for further training and reproducibility
* Tensorflow lite: Enables deployment on mobile and edge devices with lower computational cost
* Tensorflow js: Allows the model to run directly in web browsers

Model conversion is important to make the model more flexible and deployable across different platforms.

## 🧪 Results
### Best Model
* Train accuracy:
* Test accuracy:
* Precision:
* Recall:
* F1-score:
  
### Inference
    The model is tested on all 15 classes. Out of 15 classes, [X] classes are correctly predicted, showing that the model is able to generalize reasonably well on unseen data.

## 🚀 Future Work
Here are some improvement room to upgrade this project:
* Use transfer learning: This project uses a basic CNN to understand core concepts. Future work can apply pretrained models (e.g., ResNet, MobileNet) for better performance
* Deployment: Build a web or mobile application to make the model usable in real-world scenarios, such as assisting users during grocery shopping
