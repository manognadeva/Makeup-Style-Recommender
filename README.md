# Makeup Recommender System

This project is a machine learning-based web application that recommends makeup styles (eyeshadow, blush, and lipstick) tailored to a user's predicted skin tone. It integrates data preprocessing, model training, and a Flask-powered web interface to provide interactive recommendations.

## Table of Contents

- [Features](#features)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Web Application](#web-application)
- [Model Training](#model-training)
- [File Structure](#file-structure)
- [Future Enhancements](#future-enhancements)

## Features

- Predicts skin tone using a trained EfficientNetB0 model.
- Recommends makeup shades based on skin tone and user-selected categories.
- Interactive web interface for image upload and result visualization.
- Supports three categories: eyeshadow, blush, and lipstick.

## Dataset

The project utilizes the **FairFace Dataset** with a focus on Fitzpatrick skin tone classifications. The dataset is preprocessed to map Fitzpatrick skin tones into three categories: Light, Medium, and Dark.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/makeup-recommender.git
   cd makeup-recommender
   ```
2. Install the required Python packages:
   ```
   pip install -r requirements.txt```

## Usage
### Model Training

1. Update the paths for training and testing datasets in the script:
``` base_path = "/path/to/dataset/" ```
2. Run the model training script to train an EfficientNetB0-based model:
   ```python train_model.py ```

## Web Application
1. Start the Flask web server:
``` python app.py ```
2. Use the provided ngrok public URL to access the web application:
   ``` https://<ngrok-public-url> ```
3. Upload an image, select two makeup categories, and view recommendations.

# File Structure
- project/
- ├── app.py                   # Flask web application script
- ├── train_model.py           # Model training script
- ├── templates/               # HTML templates for the web app
- │   ├── index.html           # Home page
- │   └── result.html          # Results page
- ├── static/
- │   └── uploads/             # Uploaded images
- ├── requirements.txt         # Required Python packages
- ├── README.md                # Project documentation
- └── dataset/                 # Dataset folder (FairFace)

# Web Application
Home Page: Upload an image and select makeup categories.
Results Page: Displays the uploaded image, predicted skin tone, and personalized makeup recommendations.

# Model Details
The model is built using EfficientNetB0 with transfer learning:

- Base model: Pretrained on ImageNet.
- Custom layers: Global average pooling, dense layers, and a softmax output layer for skin tone classification.

## Future Enhancements

- Add more makeup categories and shades.
- Improve the model with additional features (e.g., age, gender).
- Deploy the application on a cloud platform (e.g., AWS, Heroku).
