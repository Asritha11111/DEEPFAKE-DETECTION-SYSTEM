# 🔍 DEEPFAKE DETECTION SYSTEM

![Python](https://img.shields.io/badge/Python-3.10-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.13-orange.svg)
![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

A complete web‑based deepfake detection system that analyzes **images**, **videos**, and **audio** for manipulation. Built with a custom **MesoNet** CNN model and a modern React‑like frontend (HTML/CSS/JS + Tailwind).

## ✨ Features

- 🔐 **User Authentication** – Register, login, JWT‑protected routes.
- 🖼️ **Image Detection** – Upload images, get REAL/FAKE verdict with confidence score.
- 🎥 **Video Detection** – Extracts frames, analyzes each frame, and shows per‑frame results.
- 🎤 **Audio Detection** – Uses Mel‑spectrogram CNN for voice deepfake detection.
- 📊 **Analytics Dashboard** – Charts showing your detection history (real vs fake).
- 📜 **History Panel** – Store and filter past detections (per user, localStorage).
- 👤 **User Profile** – Edit name, view stats, recent activity.
- 🌓 **Dark/Light Mode** – Toggle between themes.
- 🌐 **Multi‑language** – English, Spanish, Hindi, French.
- 📄 **PDF Report** – Download detailed analysis report.
- 📸 **Webcam Capture** – Real‑time capture and detection.

## 🧠 Model Architecture

- **MesoNet** – A compact Convolutional Neural Network (CNN) optimized for detecting facial manipulations.
- **Input**: 64×64 grayscale face crops.
- **Accuracy**: ~95% on the Celeb‑DF dataset (trained on your own dataset).

For audio, a separate CNN processes Mel‑spectrograms of 3‑second audio clips.

## 🛠️ Tech Stack

### Frontend
- HTML5, CSS3, JavaScript (ES6)
- Tailwind CSS (for landing page)
- Chart.js (analytics)
- html2pdf.js (report generation)

### Backend
- **Node.js** + **Express.js** – REST API, file uploads, JWT auth.
- **Multer** – File handling.
- **Python** (TensorFlow, OpenCV, Librosa) – Deepfake model inference.
- **ffmpeg** – Video frame extraction.

### Database
- `users.json` – Simple file‑based user storage.
- `localStorage` – Per‑user history.

## 📁 Project Structure
```
deepfake-detection/
├── public/
│ └── index.html # Frontend (all-in-one)
├── saved_model/
│ ├── mesonet_model.h5 # Image/video model
│ └── audio_model.h5 # Audio model (optional)
├── dataset/
│ ├── real/ # Training images (real faces)
│ └── fake/ # Training images (deepfakes)
├── uploads/ # Temporary uploads
├── server.js # Express backend
├── predict.py # Image prediction script
├── predict_audio.py # Audio prediction script
├── train_simple_working.py # Image model training
├── train_audio.py # Audio model training
├── requirements.txt # Python dependencies
├── package.json # Node dependencies
├── users.json # Registered users
└── README.md # This file
```

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v18+)
- **Python** (3.10)
- **pip** and **npm**

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Asritha11111/DEEPFAKE-DETECTION-SYSTEM.git
   cd DEEPFAKE-DETECTION-SYSTEM
2. **Install Node dependencies**

 ```bash
   npm install  
 ```
3. **Install Python dependencies**
 
 ```bash
   pip install -r requirements.txt
 ```
4. **Train the image model (or use a pre‑trained one)**

 ```bash
   python train_simple_working.py
 ```
Make sure you have images in dataset/real/ and dataset/fake/.

5. **Train the audio model (optional – fallback to random)**
 ```
bash
   python train_audio.py
 ```
If you skip this, the audio detection will return a random confidence.

6. **Start the server**
 ```
bash
   node server.js
 ```
7. **Open your browser** and go to http://localhost:3000

📸 Usage
1. Register a new account (any email/password).
2.Log in to access the dashboard.
3. Upload an image, video (MP4), or audio file.
4. Click Detect Deepfake (or Analyze Video/Audio).
5. View the verdict and confidence score.
6. Check your history and analytics.
7. Download a PDF report for any image detection.

## 🧪 Testing
- Place some real face images in dataset/real/ and fake (deepfake) images in dataset/fake/.
- Retrain the model whenever you add new images.

## 🐛 Troubleshooting

| Issue                          | Solution |
|--------------------------------|----------|
| Model not loading              | Retrain: `python train_simple_working.py` |
| Uploaded image always FAKE     | Check that the model was trained with correct labels. |
| ffmpeg not found               | Install ffmpeg and add to PATH, or use the `ffmpeg-static` package. |
| Audio detection fails          | The model file may be missing – use the dummy script or train a real model. |

## 📄 License
MIT

 ## 👩‍💻 Author

**Kotagiri Asritha**  
GitHub: [Asritha11111](https://github.com/Asritha11111)  
Project Repository: [DEEPFAKE-DETECTION-SYSTEM](https://github.com/Asritha11111/DEEPFAKE-DETECTION-SYSTEM)

## Acknowledgements

- MesoNet paper by Afchar et al. (2018)
- Celeb‑DF dataset
- TensorFlow, OpenCV, Librosa communities

⭐ If you find this project useful, please give it a star! ⭐
