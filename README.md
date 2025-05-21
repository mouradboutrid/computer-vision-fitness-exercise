# Exercise Form Evaluator

![Exercise Form Evaluator](https://img.shields.io/badge/Status-Active-green) ![License](https://img.shields.io/badge/License-MIT-blue) ![Python](https://img.shields.io/badge/Python-3.8%2B-yellow) ![OpenCV](https://img.shields.io/badge/OpenCV-4.x-orange) ![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-red)

A computer vision-based application that analyzes exercise form in real-time, providing instant feedback and corrections to help users maintain proper technique during workouts.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
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

## 🎬 Demo

![Demo GIF](https://via.placeholder.com/640x360.png?text=Exercise+Form+Evaluator+Demo)

## 🏗️ Technical Architecture

```
exercise-form-evaluator/
├── app/
│   ├── __init__.py
│   ├── main.py              # Application entry point
│   ├── form_analyzer.py     # Core analysis logic
│   ├── pose_detector.py     # Pose estimation module
│   ├── exercise_classifier.py  # Exercise classification module
│   ├── feedback_generator.py   # Generates correction suggestions
│   └── utils/
│       ├── __init__.py
│       ├── visualization.py    # Visualization tools
│       └── angle_calculator.py # Joint angle calculations
├── models/
│   ├── pose_model/          # Pre-trained pose estimation model
│   └── exercise_classifier/ # Exercise classification model
├── data/
│   ├── exercise_references/ # Reference data for correct form
│   └── test_videos/         # Sample videos for testing
├── ui/
│   ├── web/                 # Web interface files
│   └── desktop/             # Desktop application interface
├── tests/                   # Unit and integration tests
├── docs/                    # Documentation
├── requirements.txt         # Python dependencies
├── setup.py                 # Installation script
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
   git clone https://github.com/yourusername/exercise-form-evaluator.git
   cd exercise-form-evaluator
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
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
- Bicep curls
- Lunges
- Planks
- Shoulder press
- Deadlifts

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

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [MediaPipe](https://google.github.io/mediapipe/) for pose estimation
- [TensorFlow](https://www.tensorflow.org/) for machine learning capabilities
- [OpenCV](https://opencv.org/) for computer vision functionality
- All contributors and testers who help improve this project
