# Makeup Style Recommender

This project is a machine learning-based web application that recommends makeup styles (eyeshadow, blush, and lipstick) tailored to a user's predicted skin tone. It integrates data preprocessing, model training, and a Flask-powered web interface to provide interactive recommendations.

## Links

- [Dataset](https://drive.google.com/drive/folders/1uMfF9nHXlKFxTdF-FqFzG8-qllvzA2os?usp=sharing)
- [Figma Wireframe](https://www.figma.com/proto/DeP7RUbN8MQggXkXko3e3k/Prototype?node-id=0-1&t=H55B3G6goBb035ps-1)
- [Best Model Keras](https://drive.google.com/file/d/1cm6j33dp_2rHn6FWgbegKA7MfI1SWNzo/view?usp=sharing)

## Core Funtionality

- Skin tone prediction using a trained deep learning model
- Personalized makeup recommendations for both party and natural looks
- Interactive web interface with real-time image preview
- Support for multiple makeup categories (eyeshadow, blush, lipstick)

## Technical Implementation

- Flask-based web application with ngrok for public access
- EfficientNetB0 model architecture with transfer learning
- Responsive UI design with modern CSS styling
- Secure file handling and validation

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
   pip install -r requirements.txt
   ```

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


# Model Details
The model is built using EfficientNetB0 with transfer learning:

- Base model: Pretrained on ImageNet.
- Custom layers: Global average pooling, dense layers, and a softmax output layer for skin tone classification.

## Epoch - Model Training

<img width="1093" alt="Screenshot 2025-01-01 at 4 53 51 PM" src="https://github.com/user-attachments/assets/876d5f34-4a7e-433e-b7e9-b4e4af16670f" />


## Future Enhancements

- Expand makeup styles by incorporating additional product categories, such as concealer and bronzer recommendations.
- Introduce enhanced user features, including user profile creation for saving preferences and past recommendations.
- Accuracy Enchancement:
   - Fine-Tuning EfficientNetB0 to extract more relevant features and improve classification accuracy. Fine-tuning requires additional training epochs and more computational resources.
   - Model Ensemble to combine predictions from multiple models such as EfficientNetB0 and ResNet50, to improve robustness and overall accuracy. Ensemble learning helps reduce bias and         variance, leading to better generalization on unseen data. Implementing ensemble learning significantly increases computational and storage requirements, which requires a little more      of time to execute.
 
## Result:

### The application provides:
- Predicted skin tone classification
### Two sets of recommendations:
- Party Look: Bold and glamorous options
- No Makeup Look: Natural and subtle choices


### Step 1:

<img width="1458" alt="Screenshot 2025-01-01 at 4 23 47 PM" src="https://github.com/user-attachments/assets/ceb80ea4-7d0f-4a88-8c2d-995fc6fc91ae" />

### Step 2:

<img width="1466" alt="Screenshot 2025-01-01 at 4 24 00 PM" src="https://github.com/user-attachments/assets/e8a8a26c-f518-4efb-8b84-7f9a35a337e2" />

### Step 3:

<img width="1462" alt="Screenshot 2025-01-01 at 4 24 08 PM" src="https://github.com/user-attachments/assets/e373cc41-7c27-4304-a29e-f346d4f29bb9" />


