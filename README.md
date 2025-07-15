#PROPOSED SYSTEM

The proposed system for image forgery detection is a comprehensive approach that combines Convolutional Neural Network (CNN) architecture with Error Level Analysis (ELA) to achieve accurate and robust detection of manipulated images. This system addresses the critical need for reliable forgery detection in the era of digital image manipulation. The proposed system employs a CNN model as its core. The CNN is designed to perform feature extraction and classification of images efficiently. The model is trained on a diverse dataset comprising both authentic and tampered images. During training, it learns to identify distinctive patterns, features, and inconsistencies that indicate image manipulation. Various hyperparameters, such as the number of layers, filter sizes, and learning rates, are fine-tuned to optimize the model's performance. Appropriate activation function such as ReLU (Rectified Linear Unit), is used to introduce non-linearity in the model. 

             ![image](https://github.com/user-attachments/assets/f91fef82-9066-46b8-8b04-e63eca3ea1da)

🖼️ Image Forgery Detection System

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

🚀 Project Setup

✅ Prerequisites

Python 3.8 or higher

pip (Python package manager)

📦 Installation

1. Clone the repository:
git clone https://github.com/yourusername/image-forgery-detection.git
cd image-forgery-detection

2. Install the required dependencies:
pip install -r requirements.txt

3. Set up email credentials for OTP verification in app.py:
app.config['MAIL_USERNAME'] = 'your-email@gmail.com'
app.config['MAIL_PASSWORD'] = 'your-app-password'

4. Run the application:
python app.py

5. Visit: http://127.0.0.1:5000 in your browser.

⚙️ Implementation Details

🔸 ELA Processing

The uploaded image is compressed and compared to the original using PIL.

The resulting error image is enhanced to highlight manipulation artifacts.

🔸 CNN-Based Forgery Detection

The ELA image is resized and normalized.

The CNN model (trained_model.h5) predicts if the image is real or fake.

A confidence score is provided.

🔸 Heatmap Highlighting

For forged images, Sobel edge detection is applied.

A heatmap is overlaid on the original image to show suspect areas.

🔸 Metadata Extraction

Extracts EXIF data: camera make/model, GPS coordinates, timestamps.

Flags inconsistencies (e.g., editing software, timestamp mismatches).

🔸 User Interface & History

Flask-based routes support login, signup, OTP verification, image upload.

An analysis history is stored per user in an SQLite database.

🔸 PDF Report Generation

Users can download a report for each analysis.

Includes metadata, classification result, and heatmap image.

📈 Model Info

Input: 128x128x3 ELA images

Output: Binary classification (Real / Fake)

Framework: Keras + TensorFlow

File: trained_model.h5





