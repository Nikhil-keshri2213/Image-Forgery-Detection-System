
# 🖼️ Image Forgery Detection System using CNN + ELA

A deep learning-based system to detect **image tampering** using **Convolutional Neural Networks (CNN)** and **Error Level Analysis (ELA)**. This project helps identify whether an image is **authentic or forged**, with visual ELA outputs and a web interface for easy interaction.

---

## 📌 Table of Contents

- [🎯 Overview](#-overview)
- [🧠 How It Works](#-how-it-works)
- [🚀 Features](#-features)
- [🛠️ Technologies Used](#-technologies-used)
- [📁 Project Structure](#-project-structure)
- [💻 Installation & Setup](#-installation--setup)
- [🌐 Usage Guide](#-usage-guide)
- [📊 Model Architecture](#-model-architecture)
- [🧪 Sample Results](#-sample-results)
- [📌 Future Enhancements](#-future-enhancements)
- [📝 License](#-license)

---

## 🎯 Overview

Image tampering is a growing concern in digital media. This system uses:
- 🧠 A **CNN model** trained on **ELA-transformed images**
- 🔍 **Binary classification**: *Authentic* or *Tempered*
- 🌐 Flask-based web interface for uploading and predicting images

---

## 🧠 How It Works

1. 📤 **User Uploads an Image**
2. 🔁 **ELA (Error Level Analysis)** is performed:
   - Image is saved at 90% JPEG quality
   - The difference from the original is visualized
3. 🧠 **CNN Model** classifies the ELA image
4. ✅ **Prediction Output**:
   - Label: `Authentic` or `Tempered`
   - Model Confidence
   - ELA Visualization shown

---

## 🚀 Features

- ✅ CNN-based binary image classification
- 📷 Upload any image (PNG, JPG, TIF, BMP)
- 🔬 ELA Visualization of compression artifacts
- 📊 Real-time prediction on a Flask Web UI
- 🧰 Easily extensible and customizable

---

## 🛠️ Technologies Used

| Category          | Tools & Libraries             |
|-------------------|-------------------------------|
| Language          | Python 3.x                    |
| Deep Learning     | TensorFlow, Keras             |
| Image Processing  | Pillow (PIL), OpenCV          |
| Web Framework     | Flask                         |
| Dataset           | CASIA v2.0                    |
| Frontend          | HTML, CSS (Jinja2 templates)  |

---

## 📁 Project Structure

```
Image-Forgery-Detection/
│
├── app.py                # Flask web app
├── train_model.py        # CNN training script
├── model/                # Saved Keras model (.h5)
├── static/               # Uploaded files & ELA outputs
├── templates/            # HTML files (Flask templates)
├── utils/
│   └── ela_generator.py  # ELA creation function
├── requirements.txt      # Project dependencies
└── README.md             # This file 😄
```

---

## 💻 Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/yourusername/image-forgery-detection.git
cd image-forgery-detection
```

### 2️⃣ Install dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Run the Flask App
```bash
python app.py
```

### 4️⃣ Open in browser
```
http://127.0.0.1:5000
```

---

## 🌐 Usage Guide

1. 📤 Upload your image via the web interface
2. 🔍 System applies **ELA**
3. 🤖 CNN model predicts **Authentic** or **Tempered**
4. 📊 Displays:
   - Classification result
   - Confidence/accuracy
   - ELA image preview

---

## 📊 Model Architecture (CNN)

```python
Sequential([
    Conv2D(32, (3,3), activation='relu', input_shape=(128,128,3)),
    MaxPooling2D(2,2),
    Conv2D(64, (3,3), activation='relu'),
    MaxPooling2D(2,2),
    Conv2D(128, (3,3), activation='relu'),
    MaxPooling2D(2,2),
    Flatten(),
    Dense(128, activation='relu'),
    Dropout(0.5),
    Dense(1, activation='sigmoid')
])
```

- **ReLU** in hidden layers for non-linearity
- **Sigmoid** in output layer for binary classification
- **Dropout** to prevent overfitting
- Trained on ELA images from CASIA2 dataset

---

## 🧪 Sample Results

| Input Image | ELA Visualization | Prediction |
|-------------|-------------------|------------|
| ![](temp.jpg) | ![](temp_file_name.jpg) | **Tempered** |

---

## 📌 Future Enhancements

- 🔍 Add **forgery localization** with segmentation (e.g. U-Net)
- 💡 Integrate **DCT, Zigzag, and Quantization**
- 🖼️ Real-time webcam support
- ☁️ Deploy on **AWS / Heroku / Streamlit**

---

## 📝 License

This project is licensed under the MIT License.  
Feel free to use, modify, and contribute with attribution.

---

## 🙋‍♂️ Author

**Nikhil Keshri**  
B.Tech CSE | Computer Science Enthusiast |   
📧 Email: nikhilkeshri2213@gmail.com

---

⭐ *If you found this useful, don't forget to star the repo and share it!*