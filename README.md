# Brain-Tumor-Segmentation
A deep learning-based web application for brain tumor classification and exploratory data analysis (EDA), built using TensorFlow, Gradio, Streamlit, and Google Colab. The app allows interactive visualization of tumor datasets and real-time prediction of tumor types from uploaded MRI images.
🔍 Features
📊 EDA Dashboard using Streamlit (Ngrok-enabled)

🧠 Tumor Classification using CNNs (Convolutional Neural Networks)

📁 Four Classes: glioma, meningioma, notumor, pituitary

📷 Image upload & classification via Gradio UI

⚙️ Trained in Google Colab, works with Google Drive for data loading

📁 Dataset
The dataset must follow this folder structure inside your Google Drive:

Brain Tumor Segmentation/
├── glioma/
├── meningioma/
├── notumor/
└── pituitary/
Each folder contains relevant MRI images for that tumor class.

Example dataset path in the code:


/content/drive/MyDrive/Brain Tumor Segmentation
🛠️ Requirements
Install all required packages in Colab:
!pip install streamlit pyngrok gradio
🚀 How to Run in Google Colab
Mount your Google Drive:
from google.colab import drive
drive.mount('/content/drive')
Write and launch the Streamlit EDA App:
%%writefile app.py
# [Paste your Streamlit EDA code here]
!streamlit run app.py &
from pyngrok import ngrok
ngrok.set_auth_token("your-ngrok-token")
public_url = ngrok.connect(8501)
print(f"Streamlit app is live at: {public_url}")
Build & Train CNN model with Gradio Interface:

All model training and prediction logic is in the main notebook. Gradio will automatically launch a GUI after training:
interface.launch()
📊 Streamlit EDA Dashboard
Displays number of images per class

Resize images for EDA analysis

Easy to modify paths via UI

🧪 CNN Architecture (Keras)
Conv2D -> MaxPool -> BatchNorm
Conv2D -> MaxPool -> BatchNorm
Conv2D -> MaxPool -> BatchNorm
GlobalAveragePooling -> Dense(128) -> Dropout -> Dense(4)
Loss Function: categorical_crossentropy
Optimizer: Adam
Metrics: accuracy

📷 Gradio Interface
After training the CNN, launch the classifier:

Upload an MRI image

Instantly get the predicted tumor type

Works with images of shape (128, 128)

📌 Notes
Replace "your-ngrok-token" with your actual Ngrok auth token.

Use GPU runtime in Colab for faster training.

Dataset should be pre-downloaded and uploaded to Google Drive.
