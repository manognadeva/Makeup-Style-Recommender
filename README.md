# Makeup Recommender System

This project is a machine learning-based web application that recommends makeup styles (eyeshadow, blush, and lipstick) tailored to a user's predicted skin tone. It integrates data preprocessing, model training, and a Flask-powered web interface to provide interactive recommendations.

## Links

- [Dataset](https://drive.google.com/drive/folders/1uMfF9nHXlKFxTdF-FqFzG8-qllvzA2os?usp=sharing)
- [Figma Wireframe](https://www.figma.com/proto/DeP7RUbN8MQggXkXko3e3k/Prototype?node-id=0-1&t=H55B3G6goBb035ps-1)
- [Best Model Keras](https://drive.google.com/file/d/1cm6j33dp_2rHn6FWgbegKA7MfI1SWNzo/view?usp=sharing)

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

## Epoch - Model Training

<img width="1470" alt="Screenshot 2024-12-31 at 8 53 02 PM" src="https://github.com/user-attachments/assets/b389eea1-5a07-4a06-9f36-9cb156f2add0" />

## Future Enhancements

- Add more makeup categories and shades.
- Improve the model with additional features (e.g., age, gender).
- Deploy the application on a cloud platform (e.g., AWS, Heroku).


## Result:
### Step 1:

<img width="1458" alt="Screenshot 2025-01-01 at 4 23 47 PM" src="https://github.com/user-attachments/assets/ceb80ea4-7d0f-4a88-8c2d-995fc6fc91ae" />

### Step 2:

<img width="1466" alt="Screenshot 2025-01-01 at 4 24 00 PM" src="https://github.com/user-attachments/assets/e8a8a26c-f518-4efb-8b84-7f9a35a337e2" />

### Step 3:

<img width="1462" alt="Screenshot 2025-01-01 at 4 24 08 PM" src="https://github.com/user-attachments/assets/e373cc41-7c27-4304-a29e-f346d4f29bb9" />


