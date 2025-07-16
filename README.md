# PFE_2025_DA2I_C22580_Ramla_Babaha
A deepfake detection model based on EfficientNetB0 and MTCNN for face detection is a deep learning-based project for detecting AI-generated deepfake images. This project was developed as part of my final year graduation project and features a web-based interface to visualize the detection process. It utilizes an EfficientNetB0 CNN model trained on multiple state-of-the-art deepfake datasets.

## 🔍 Description

This project aims to train and serve a deepfake detection model using Python, TensorFlow, and Keras. The CNN model is based on **EfficientNetB0** and fine-tuned to classify faces as *real* or *deepfake*.

The application includes:

- A deep learning model trained on balanced and preprocessed datasets
- A face extraction pipeline using **MTCNN**
- A web interface built using **Flask**, **HTML**, and **CSS** for interactive use
- Visualization of detection with bounding boxes for identified faces

## 🧾 Datasets Used

The training was based on a combination of multiple high-quality public datasets to ensure robustness and variety in fake generation methods:

- **DeepFake-TIMIT**
- **FaceForensics++**
- **Google DeepFake Detection (DFD)**
- **Celeb-DF**
- **Facebook Deepfake Detection Challenge (DFDC)**

> The final dataset includes over **402,000 images**, **1,140 unique identities**, and **20+ synthesis methods**.

## 🛠 Getting Started

### ✅ Prerequisites

- Python 3.x
- TensorFlow / Keras
- EfficientNet for TensorFlow
- OpenCV
- MTCNN

Install dependencies:

```bash
pip install -r requirements.txt
````

### 📂 Usage Workflow

#### Step 0: Extract video frames

```bash
python convert_video_to_image.py
```

This script converts deepfake/real videos into individual frame images and resizes them based on resolution.

#### Step 1: Face Detection and Cropping

```bash
python crop_faces_with_mtcnn.py
```

Uses MTCNN to detect and crop faces from frame images, adding margin and filtering with confidence score.

#### Step 2: Balance and Split Datasets

```bash
python prepare_fake_real_dataset.py
```

Ensures dataset balance (fake vs. real) and splits data into train/val/test sets.

#### Step 3: Train the CNN Model

```bash
python train_cnn.py
```

Trains the EfficientNetB0 model (modified input/output layers) as a binary classifier.

#### Step 4: Run Web App

```bash
python app.py
```

Launches the Flask-based web interface for uploading and detecting deepfake images.

## 🖼 Web Interface Features

* Upload image for real/fake detection
* Display of bounding boxes on detected faces
* Probability score for each face
* Clean and intuitive UI (HTML/CSS)

## 🤖 Model Architecture

The CNN is based on **EfficientNetB0**, modified as follows:

* Input size: 128x128x3
* Backbone: EfficientNetB0 (pretrained on ImageNet)
* Custom FC layers with ReLU and Dropout
* Output: Sigmoid activation for binary classification

## 🧑‍💻 Author

**Ramla**
Bachelor’s Final Year Project — University of Nouakchott
📧 Email: [ramlebabaha32@gmail.com](mailto:ramlebabaha32@gmail.com)
📍 Location: Nouakchott, Mauritania

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments



* Special thanks to my academic advisor and jury panel

---

> 🧠 This project was developed with the goal of enhancing media literacy and promoting AI ethics through practical machine learning applications.
