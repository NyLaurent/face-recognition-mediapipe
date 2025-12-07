# 🎭 Face Recognition System

A real-time face recognition system built with Python, MediaPipe, and OpenCV's LBPH algorithm. This project allows you to collect face data, train a recognition model, and perform real-time face identification using your webcam.

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Latest-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📋 Table of Contents

- [Features](#features)
- [How It Works](#how-it-works)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

- **Real-time Face Detection**: Uses MediaPipe Face Mesh for accurate face detection
- **LBPH Recognition**: Implements Local Binary Patterns Histograms for face recognition
- **Easy Data Collection**: Simple interface to capture training images
- **Live Recognition**: Real-time face identification with confidence scores
- **Multiple Faces Support**: Train the system to recognize multiple people
- **Lightweight**: Minimal dependencies and fast processing

## 🔍 How It Works

The system operates in three stages:

1. **Data Collection** (`record.py`): Captures face images from your webcam and stores them in organized folders
2. **Model Training** (`train.py`): Trains an LBPH face recognizer using the collected images
3. **Face Recognition** (`predict.py`): Performs real-time face recognition using the trained model

### Algorithm Overview

- **Face Detection**: MediaPipe Face Mesh detects faces and extracts facial landmarks
- **Face Recognition**: OpenCV's LBPH (Local Binary Patterns Histograms) algorithm compares facial features
- **Confidence Scoring**: Lower scores indicate higher confidence in recognition

## 🚀 Installation

### Prerequisites

- Python 3.7 or higher
- Webcam/Camera
- pip (Python package manager)

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/face-recognition.git
cd face-recognition
```

### Step 2: Install Dependencies

```bash
pip install opencv-python opencv-contrib-python mediapipe numpy
```

Or install from requirements file (if available):

```bash
pip install -r requirements.txt
```

### Dependencies List

- `opencv-python` - Computer vision library
- `opencv-contrib-python` - Additional OpenCV modules (includes face recognition)
- `mediapipe` - Face detection and landmark tracking
- `numpy` - Numerical operations

## 📖 Usage

Follow these steps to set up and use the face recognition system:

### Step 1: Collect Face Data

Run the data collection script to capture face images:

```bash
python record.py
```

**Instructions:**
1. Enter the person's name when prompted
2. Position your face in front of the camera
3. The system will automatically capture face images
4. Move your head slightly to capture different angles
5. Press `q` to stop recording

**Tip**: Capture 50-100 images per person for better accuracy

### Step 2: Train the Model

After collecting data for all people, train the recognition model:

```bash
python train.py
```

This will:
- Load all images from the `dataset/` folder
- Train the LBPH face recognizer
- Save the model to `models/lbph_model.xml`
- Save the label mapping to `models/label_map.json`

### Step 3: Run Face Recognition

Start the real-time face recognition:

```bash
python predict.py
```

**Instructions:**
1. The webcam will activate and show a live feed
2. Detected faces will be highlighted with green rectangles
3. Recognized faces will display the person's name and confidence score
4. Unknown faces will be labeled as "Unknown"
5. Press `q` to quit

## 📁 Project Structure

```
face-recognition/
│
├── record.py              # Data collection script
├── train.py               # Model training script
├── predict.py             # Real-time recognition script
├── README.md              # Project documentation
│
├── dataset/               # Training images (created automatically)
│   ├── Person1/
│   │   ├── 0.jpg
│   │   ├── 1.jpg
│   │   └── ...
│   ├── Person2/
│   │   └── ...
│   └── ...
│
└── models/                # Trained models (created automatically)
    ├── lbph_model.xml     # Trained LBPH face recognizer
    └── label_map.json     # Label to name mapping
```

## 🛠️ Technologies Used

- **[Python](https://www.python.org/)** - Programming language
- **[OpenCV](https://opencv.org/)** - Computer vision and face recognition
- **[MediaPipe](https://mediapipe.dev/)** - Face detection and landmark tracking
- **[NumPy](https://numpy.org/)** - Numerical computing
- **LBPH Algorithm** - Local Binary Patterns Histograms for face recognition

## 🔧 Troubleshooting

### Camera Not Found

If you get a camera error:
- Check if your camera is connected and working
- Try changing the camera index in the scripts:
  - `record.py`: Line 11 - `cv2.VideoCapture(1)` → try `0`, `1`, or `2`
  - `predict.py`: Line 15 - `cv2.VideoCapture(0)` → try `0`, `1`, or `2`

### Model Not Found Error

If you get "models/lbph_model.xml not found":
- Make sure you've run `train.py` before `predict.py`
- Check that the `models/` directory exists and contains the model files

### Poor Recognition Accuracy

To improve accuracy:
- Collect more training images (100+ per person recommended)
- Ensure good lighting conditions during data collection
- Capture images from different angles and expressions
- Retrain the model after adding more images

### Import Errors

If you get module import errors:
```bash
pip install --upgrade opencv-python opencv-contrib-python mediapipe numpy
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- MediaPipe team for the excellent face detection library
- OpenCV community for the face recognition algorithms
- All contributors and users of this project

## 📧 Contact

Your Name - [@NyLaurent](https://github.com/NyLaurent)

Project Link: [https://github.com/NyLaurent/face-recognition](https://github.com/NyLaurent/face-recognition)

---

⭐ If you found this project helpful, please give it a star!
# face-recognition-mediapipe
