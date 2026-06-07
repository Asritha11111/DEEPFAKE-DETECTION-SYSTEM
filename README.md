# 🎭 Deepfake Recognition System

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.13-orange.svg)](https://tensorflow.org)
[![React](https://img.shields.io/badge/React-18.2-blue.svg)](https://reactjs.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Detect AI‑generated fake videos and images with an intuitive web interface**

A complete end‑to‑end deepfake detection system that uses the **MesoNet** convolutional neural network to identify manipulated facial media. The system provides a user‑friendly web interface, real‑time predictions, and model training capabilities – all optimised to run on standard CPUs.

![System Architecture](docs/architecture.png) <!-- Add your actual screenshot later -->

---

## ✨ Features

- 🧠 **Deep Learning Detection** – MesoNet CNN trained to spot facial manipulations
- 🌐 **Web‑based UI** – Built with React + Chakra UI, drag‑and‑drop uploads
- ⚡ **CPU Optimised** – No GPU required; runs efficiently on standard hardware
- 📸 **Image & Video Support** – Analyse single images or frame‑by‑frame video
- 📊 **Confidence Scores** – Percentage probability of real vs. fake
- 🏋️ **Train Your Own Model** – Use custom datasets for fine‑tuning
- 📈 **Real‑time Progress** – Training and prediction feedback with live metrics

---

## 🧠 How It Works

1. **Upload** an image or video through the web interface
2. **Preprocessing** – Faces are detected, aligned, resized to 64×64 grayscale
3. **MesoNet Model** – A compact CNN extracts hierarchical features
4. **Prediction** – Outputs a score:
   - `> 0.5` → **REAL**
   - `≤ 0.5` → **DEEPFAKE**
5. **Result** – Shown with confidence percentage and visual indicators

![Detection Pipeline](docs/pipeline.png) <!-- Add diagram later -->

---

## 🛠️ Tech Stack

| Layer          | Technologies                                                                 |
|----------------|------------------------------------------------------------------------------|
| **Frontend**   | React 18, Chakra UI, Vite, Axios                                            |
| **Backend**    | Node.js, Express, Multer, Python‑Shell                                      |
| **ML Engine**  | Python 3.8+, TensorFlow (CPU), OpenCV, NumPy, scikit‑learn                  |
| **Model**      | MesoNet (custom CNN with 3 conv blocks + dense layers)                      |
| **Deployment** | Local server (easily containerised with Docker)                             |

---

``` ## 📁 Project Structure
deepfake-detection/
├── model/
│ └── mesonet.py # MesoNet neural network architecture
├── scripts/ # Utility scripts (organise, process, etc.)
├── src/
│ ├── components/ # React UI components
│ ├── App.jsx # Main React app
│ └── main.jsx # Entry point
├── utils/
│ ├── data_loader.py # Dataset loading utilities
│ ├── logger.py # Logging helper
│ └── video_to_frames.py # Frame extraction
├── dataset/ # Training data (real/ and fake/ subfolders)
├── saved_model/ # Trained model (.h5 file)
├── uploads/ # Temporary file storage
├── server.js # Express backend
├── train.py # Model training script
├── predict.py # Prediction script
├── package.json # Node dependencies
├── requirements.txt # Python dependencies
├── vite.config.js # Vite configuration
└── index.html # Main HTML entry point
``` 

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v14+ recommended) – [Download](https://nodejs.org)
- **Python** (3.8 – 3.10) – [Download](https://python.org)
- **npm** (comes with Node.js)
- **pip** (comes with Python)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/deepfake-detection.git
   cd deepfake-detection
Install Node dependencies

bash
npm install
Install Python dependencies

bash
pip install -r requirements.txt
Prepare dataset (optional for training)

Put real face images in dataset/real/

Put deepfake images in dataset/fake/

Supported formats: .jpg, .png, .jpeg

Running the Application
You need two terminals – one for backend, one for frontend.

Terminal 1 – Backend
bash
node server.js
Expected output:

🚀 Server running on http://localhost:3000
Terminal 2 – Frontend
bash
npm run dev
Expected output:

text
VITE ready...
➜ Local: http://localhost:5173/
Open your browser at http://localhost:5173 and start detecting!

Training the Model
Place your training images in dataset/real/ and dataset/fake/

In the web UI, go to Train Model tab

Set number of epochs (e.g., 50) and batch size (e.g., 32)

Click Start Training – progress will be shown in the terminal

The trained model is saved to saved_model/mesonet_model.h5

📊 Results & Performance
Tested on the Celeb-DF dataset (v2) with 50 epochs:

Metric	Value
Accuracy	95.23%
Precision	94.87%
Recall	95.61%
F1 Score	95.24%
Inference time (image)	~1.2 seconds
Performance may vary depending on CPU and dataset size.

🔮 Future Enhancements
GPU acceleration (CUDA support for faster training)

Real‑time video stream analysis

Ensemble models (combine MesoNet with Xception / EfficientNet)

Batch processing for multiple files

Docker containerisation for easy deployment

Explainable AI (heatmaps showing manipulated regions)

📚 References
Afchar et al. – MesoNet: a Compact Facial Video Forgery Detection Network (WIFS 2018)

Rossler et al. – FaceForensics++ (ICCV 2019)

Li et al. – Celeb-DF: A Large-scale Challenging Dataset for DeepFake Forensics (CVPR 2020)

TensorFlow Documentation

OpenCV Documentation

👨‍💻 Author
## 👨‍💻 Author

**Your Name**  
Student, Computer Science  
GitHub: [@Asritha11111](https://github.com/Asritha11111)

📄 License
This project is licensed under the MIT License – see the LICENSE file for details.

🙏 Acknowledgements
Department of Computer Science, TKR College

SBTET Telangana for the academic framework

Open‑source community for TensorFlow, React, Chakra UI, and Express

⚠️ Disclaimer
This system is intended for research and educational purposes only. It may not be 100% accurate against all deepfake generation methods. Always use critical thinking when evaluating digital media.

