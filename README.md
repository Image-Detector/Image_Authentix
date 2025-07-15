#PROPOSED SYSTEM

The proposed system for image forgery detection is a comprehensive approach that combines Convolutional Neural Network (CNN) architecture with Error Level Analysis (ELA) to achieve accurate and robust detection of manipulated images. This system addresses the critical need for reliable forgery detection in the era of digital image manipulation. The proposed system employs a CNN model as its core. The CNN is designed to perform feature extraction and classification of images efficiently. The model is trained on a diverse dataset comprising both authentic and tampered images. During training, it learns to identify distinctive patterns, features, and inconsistencies that indicate image manipulation. Various hyperparameters, such as the number of layers, filter sizes, and learning rates, are fine-tuned to optimize the model's performance. Appropriate activation function such as ReLU (Rectified Linear Unit), is used to introduce non-linearity in the model. 

![image](https://github.com/user-attachments/assets/f91fef82-9066-46b8-8b04-e63eca3ea1da)

Image Forgery Detection System

This project is a web-based AI system that detects whether an image is forged or authentic using deep learning and image forensics. It integrates Error Level Analysis (ELA), Convolutional Neural Networks (CNN), and EXIF metadata analysis into a Flask-based web application with authentication and report generation features.

🔍 Features

✅ Detects whether an image is Real or Fake

🔥 ELA Heatmaps highlight possible tampered regions

🧐 Deep Learning Model (CNN) trained on ELA images

📷 Extracts and analyzes EXIF metadata (camera info, GPS, timestamps)

📄 Generates PDF analysis reports with all results and visual outputs

🔐 Secure user authentication and OTP-based verification

🔢 Full analysis history and report download options

🌐 Includes REST API endpoint for programmatic analysis

🚀 How It Works

Image Upload: User uploads an image through the web interface or API.

ELA Conversion: Image is compressed and compared to the original to reveal possible manipulations.

CNN Prediction: ELA-transformed image is passed to a trained CNN model for classification.

Heatmap Highlighting: If forged, manipulated areas are shown using heatmaps (via Sobel filters and OpenCV).

Metadata Analysis: The app extracts EXIF data like camera info, GPS location, timestamps, and validates them.

PDF Report: Results are compiled into a downloadable report with image, prediction, and metadata.

📁 Project Structure

.
├── app.py                # Flask backend with all routes and logic
├── forgery_detection.py  # Forgery analysis functions and model
├── templates/            # Jinja2 HTML templates
├── static/               # CSS/JS/image assets
├── uploads/              # Uploaded and processed image storage
├── reports/              # Generated PDF reports
├── trained_model.h5      # Trained CNN model file
└── requirements.txt      # Python dependencies

🚧 Installation & Setup

Prerequisites

Python 3.8+

pip

Install

git clone https://github.com/yourusername/image-forgery-detection.git
cd image-forgery-detection
pip install -r requirements.txt

Run

python app.py

Visit http://127.0.0.1:5000 in your browser.

Email Configuration

Edit app.py:

app.config['MAIL_USERNAME'] = 'your-email@gmail.com'
app.config['MAIL_PASSWORD'] = 'your-app-password'

Use Gmail App Passwords if 2FA is enabled.

📲 API Endpoint

POST /api/detect-forgery

curl -X POST -F "file=@/path/to/image.jpg" http://localhost:5000/api/detect-forgery

Response:

{
  "success": true,
  "result": "Fake",
  "confidence": 97.45,
  "metadata": {
    "camera_model": "Canon EOS",
    "location": "17° 22' 23.45\" N, 78° 29' 12.78\" E",
    ...
  }
}

📈 Model Info

Input: 128x128x3 ELA images

Output: Binary classification (Real / Fake)

Framework: Keras + TensorFlow

File: trained_model.h5





