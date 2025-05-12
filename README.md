# 🧠 Brain Tumor Segmentation using Computer Vision

This project is a deep learning-based brain tumor classification system using **Convolutional Neural Networks (CNNs)**. It classifies MRI brain scan images into four categories: **glioma**, **meningioma**, **pituitary**, and **no tumor**. A simple **Gradio** interface is also provided for real-time predictions.

---

## 🔍 Project Overview

Brain tumor detection is crucial for early diagnosis and treatment planning. This project aims to automate the classification process using a CNN trained on MRI scans. The goal is to assist radiologists and healthcare professionals in identifying brain tumor types with high accuracy.

---

## 📁 Dataset

- 📦 **Location:** Stored in Google Drive  
- 🧾 **Structure:**  
/dataset
├── glioma/
├── meningioma/
├── notumor/
└── pituitary/

- 🖼️ Images are resized to **128x128** pixels before training.

---

## 🧠 Model Architecture

A Convolutional Neural Network (CNN) built using TensorFlow/Keras with the following architecture:

Conv2D (32) + ReLU → MaxPooling2D → BatchNormalization
Conv2D (64) + ReLU → MaxPooling2D → BatchNormalization
Conv2D (128) + ReLU → MaxPooling2D → BatchNormalization
→ GlobalAveragePooling2D
→ Dense (128) + ReLU + Dropout
→ Dense (4) + Softmax

---

## 📊 Training Configuration

- **Image Size:** 128x128  
- **Batch Size:** 16  
- **Epochs:** 10  
- **Optimizer:** Adam  
- **Loss Function:** Categorical Crossentropy  
- **Metric:** Accuracy  
- **Data Split:** 80% training / 20% testing

---

## 🚀 How to Run

1. **Mount Google Drive** (Dataset stored in Drive)
2. **Install dependencies**  
   ```bash
   pip install tensorflow opencv-python numpy scikit-learn gradio
Train the Model
Recommended: Run on Google Colab

Launch Gradio Interface
interface.launch()
🖼️ Gradio Interface
Upload an MRI image (PNG/JPG)

The model predicts one of:

Glioma

Meningioma

Pituitary

No Tumor

🧪 Sample Prediction Code
def predict_image(image):
    image = cv2.cvtColor(np.array(image), cv2.COLOR_RGB2BGR)
    image = cv2.resize(image, (128, 128))
    image = np.expand_dims(image, axis=0) / 255.0
    prediction = model.predict(image)
    label = lb.inverse_transform(prediction)
    return label[0]
📌 Requirements
Python 3.x

TensorFlow / Keras

OpenCV

NumPy

scikit-learn

Gradio

Google Colab (recommended)

📈 Future Improvements
✅ Use transfer learning (EfficientNet, ResNet)

✅ Add segmentation (e.g., U-Net)

✅ Integrate Grad-CAM for visual interpretability

✅ Improve UI and deploy via Flask or Streamlit

✅ Add model performance metrics dashboard

📜 License
This project is licensed under the MIT License.
Feel free to use, modify, and share!

🙌 Acknowledgments
Dataset: [Kaggle / Public MRI Repositories]

Frameworks: TensorFlow, Keras, OpenCV, scikit-learn, Gradio

Inspiration: Medical imaging research and healthcare AI applications
