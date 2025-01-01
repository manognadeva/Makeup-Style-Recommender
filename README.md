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
- ResNet50V2 model architecture with transfer learning
- Responsive UI design with modern HTML/CSS styling
- Secure file handling and validation

## Dataset

The project utilizes the [FairFace Dataset](https://www.kaggle.com/code/kaiju8/race-classification-using-pytorch/input?select=fairface) with a focus on Fitzpatrick skin tone classifications. The dataset is preprocessed to map Fitzpatrick skin tones into three categories: Light, Medium, and Dark.

## Running the App

- Install Jupyter Notebook or open SLAY_Project_Assessment.ipynb in Google colab.
- Download the dataset or move it your google drive from the above link
- Run the first two nodes in Google colab and give access to drive when asked to obtain the dataset
- Create an account in Ngrok and create a authtoken. This token will allow the google colab to access public url outside its designated cloud.
- Run each node. This will train a model and save it in google colab following which a flask app will be started.

## Web Application

1. Click on the provided ngrok public URL to access the web application that comes up after running the colab:
   ``` https://<ngrok-public-url> ```
2. Upload an image, select two makeup categories, and view recommendations.

# File Structure
         
- ├── templates/               # HTML templates for the web app
- │   ├── index.html           # Home page
- │   └── result.html          # Results page
- ├── static/
- │   └── uploads/             # Uploaded images
- ├──  SLAY_Project_Assessment.ipynb       
- ├── README.md                # Project documentation



# Model Details
The model is built using ResNet50V2 with transfer learning.

#### Base model: 
- Pretrained on ImageNet
#### Custom layers:
- Data augmentation (random brightness, contrast, and horizontal flip)
- Global average pooling
- Batch normalization
- Dropout
- Dense layers with ReLU activation and L2 regularization
- Softmax output layer for skin tone classification (Light, Medium, Dark).

The model uses transfer learning by freezing all layers except the last 30 of the ResNet50V2 base. It is compiled with Adam optimizer and categorical crossentropy loss for the skin tone classification task.

## Epoch - Model Training

<img width="1093" alt="Screenshot 2025-01-01 at 4 53 51 PM" src="https://github.com/user-attachments/assets/876d5f34-4a7e-433e-b7e9-b4e4af16670f" />


## Future Enhancements

- Expand makeup styles by incorporating additional product categories, such as concealer and bronzer recommendations.
- Introduce enhanced user features, including user profile creation for saving preferences and past recommendations.
- Accuracy Enchancement:
   - Fine-Tuning ResNet50 to extract more relevant features and improve classification accuracy. Fine-tuning requires additional training epochs and more computational resources.
   - Model Ensemble to combine predictions from multiple models such as ResNet50V2 and ResNet50, to improve robustness and overall accuracy. Ensemble learning helps reduce bias and         variance, leading to better generalization on unseen data. Implementing ensemble learning significantly increases computational and storage requirements, which requires a little more      of time to execute.
 
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


