# Exercise Form Evaluator

A computer vision-based application that analyzes exercise form in real-time, providing instant feedback and corrections to help users maintain proper technique during workouts.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technical Architecture](#technical-architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Supported Exercises](#supported-exercises)
- [How It Works](#how-it-works)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## 🔍 Overview

Exercise Form Evaluator is an intelligent fitness assistant that uses computer vision to analyze and provide feedback on exercise techniques. Whether you're doing squats, push-ups, or bicep curls, this application helps ensure you're performing exercises correctly to maximize effectiveness and prevent injuries.

The system works with:
- Real-time camera input from your webcam
- Uploaded video files for analysis
- Various common strength and conditioning exercises

## ✨ Features

- **Real-time Exercise Classification**: Automatically identifies which exercise you're performing
- **Form Analysis**: Tracks key body points and evaluates form against correct technique models
- **Personalized Feedback**: Provides specific suggestions to correct form issues
- **Progress Tracking**: Monitors improvement over time
- **Exercise Library**: Supports multiple common exercises with expansion capability
- **User-friendly Interface**: Simple controls for video upload or camera activation

## 🏗️ Technical Architecture

```
exercise-form-evaluator/
├── app/...
├── models/
│   ├── exercise_tracker/                     # Pre-trained pose estimation model (only for push-ups and squat)
│   └── exercise_classifier/ # Exercise classification model
├── data/
│   └── test_video/         # Sample videos for testing
├── data_processing/        # From raw videos to Array of landmarks positions 
│   ├── data_Preprocessing.ipynb 
│   ├── data_analyzer.ipynb 
│   ├── X.npy               #landmarks position with weights
│   └── y.npy               #Labels
├── src/
│   ├── exercise_classifier.ipynb
│   ├── Squat_form_tracker.ipynb
│   └── pushup_from_tracker.ipynb
├── requirements.txt         # Python dependencies
└── README.md                # This file
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- Webcam (for real-time analysis)
- GPU recommended for faster processing

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/mouradboutrid/computer-vision-fitness-exercise.git
   cd exercise-form-evaluator
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Download required models:
   ```bash
   python setup.py download_models
   ```

## 💻 Usage

### Running with Live Camera

```bash
python -m app.main --source camera
```

### Analyzing a Video File

```bash
python -m app.main --source video --input path/to/your/video.mp4
```

### Web Interface

1. Start the web server:
   ```bash
   python -m app.main --interface web
   ```

2. Open your browser and navigate to `http://localhost:8000`

## 🏋️‍♂️ Supported Exercises

The current version supports the following exercises:
- Squats
- Push-ups
Additional exercises will be added in future updates.

## ⚙️ How It Works

1. **Pose Detection**: Using MediaPipe or OpenPose to detect human body keypoints
2. **Exercise Classification**: ML model identifies which exercise is being performed
3. **Form Analysis**: Compares joint angles and positions with correct form references
4. **Feedback Generation**: Creates specific, actionable feedback based on detected issues
5. **Visualization**: Displays feedback and form correction guides on the input video

### Key Technologies

- **OpenCV**: Video processing and visualization
- **TensorFlow/PyTorch**: Deep learning framework for pose estimation and classification
- **MediaPipe**: Human pose tracking
- **Flask/FastAPI**: Web interface backend (if using web interface)
- **NumPy**: Numerical computations for angle calculations

  
## 🙏 Acknowledgments

- [MediaPipe](https://google.github.io/mediapipe/) for pose estimation
- [TensorFlow](https://www.tensorflow.org/) for machine learning capabilities
- [OpenCV](https://opencv.org/) for computer vision functionality
- All contributors and testers who help improve this project
