# 🏋️ AI Gym Coach

An AI-powered real-time fitness coaching application that uses **MediaPipe Pose Estimation**, **OpenCV**, **Streamlit**, and **LLM-powered voice coaching** to monitor exercise form, count repetitions, provide live feedback, and track workout progress.

---

# Features

- 🎥 Real-time pose detection using webcam
- 💪 Exercise repetition counting
- ✅ Form correction and posture analysis
- 🤖 AI voice coach powered by Groq LLM
- 🔊 Text-to-Speech workout guidance
- 📊 Workout history and progress tracking
- 👤 Simple login/session management
- 🎨 Modern Streamlit interface
- 📱 Responsive landing page

---

# Tech Stack

| Category | Technology |
|----------|------------|
| Frontend | Streamlit |
| Computer Vision | MediaPipe Pose |
| Image Processing | OpenCV |
| Machine Learning | MediaPipe Pose Landmarker |
| AI Coach | Groq API |
| Voice | gTTS |
| Database | Local SQLite (Exercise Repository) |
| Data Analysis | Pandas |

---

# Supported Exercises

The application currently supports:

- Push Ups
- Squats
- Lunges
- Biceps Curl
- Shoulder Press

Each detector performs:

- Pose validation
- Rep counting
- Form analysis
- Feedback generation

---

# Project Architecture

```
AI-GYM-COACH
│
├── LandingPage/
│   ├── fonts/
│   ├── IMGs_add_your_own/
│   ├── videos_add_your_own/
│   ├── index.html
│   └── style.css
│
├── Main App/
│   │
│   ├── main.py                  # Streamlit application entry point
│   ├── requirements.txt
│   ├── packages.txt
│   │
│   ├── core/
│   │   └── base_exercise.py
│   │
│   ├── detectors/
│   │   ├── pushup.py
│   │   ├── squat.py
│   │   ├── lunges.py
│   │   ├── biceps_curl.py
│   │   └── shoulder_press.py
│   │
│   ├── ml_models/
│   │   └── pose_landmarker_full.task
│   │
│   ├── services/
│   │   ├── auth/
│   │   ├── coaching/
│   │   ├── config/
│   │   ├── persistence/
│   │   ├── state/
│   │   ├── tracking/
│   │   ├── ui/
│   │   └── vision/
│   │
│   ├── static/
│   │   ├── style.css
│   │   └── AdobeClean.otf
│   │
│   ├── tutorial-info/
│   │
│   └── pages/
│
└── README.md
```

---

# System Architecture

```
                 Webcam
                    │
                    ▼
            OpenCV Video Capture
                    │
                    ▼
         MediaPipe Pose Detection
                    │
                    ▼
          Exercise Detector Module
                    │
        ┌───────────┼────────────┐
        ▼           ▼            ▼
   Rep Counter   Form Check   Metrics
        │           │            │
        └───────────┼────────────┘
                    ▼
             Streamlit Dashboard
                    │
                    ▼
           Groq AI Workout Coach
                    │
                    ▼
             Text-to-Speech Output
```

---

# Module Overview

## `main.py`

Main application entry point.

Responsibilities:

- Initialize Streamlit
- User authentication
- Session management
- Webcam streaming
- Workout selection
- Voice coaching
- Metrics display

---

## `core/`

Contains the reusable base exercise class that provides common functionality for all exercise detectors.

---

## `detectors/`

Implements exercise-specific logic.

Each detector is responsible for:

- Landmark extraction
- Angle calculation
- Stage detection
- Rep counting
- Form validation
- Feedback generation

Current detectors include:

- Push Up
- Squat
- Lunges
- Shoulder Press
- Biceps Curl

---

## `services/`

Contains reusable business logic.

### auth/

Authentication and login components.

### coaching/

AI coaching services.

Includes:

- LLM integration
- Voice pipeline
- Text-to-Speech

### config/

Workout configuration and exercise options.

### persistence/

Stores workout history and exercise records.

### state/

Manages Streamlit session state.

### tracking/

Tracks workout metrics.

### ui/

Loads CSS, fonts, and custom UI.

### vision/

Processes webcam frames and pose estimation.

---

## `ml_models/`

Contains the MediaPipe Pose Landmarker model used for pose estimation.

---

## `static/`

Stores application assets including:

- Fonts
- CSS

---

## `LandingPage/`

Static landing page before launching the Streamlit application.

Contains:

- HTML
- CSS
- Fonts
- Media placeholders

---

# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/ai-gym-coach.git

cd ai-gym-coach
```

---

## Create Virtual Environment

Windows

```bash
python -m venv venv

venv\Scripts\activate
```

Linux / macOS

```bash
python3 -m venv venv

source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Environment Variables

Create a `.env` file inside the project directory.

```
GROQ_API_KEY=your_api_key_here
```

---

# Run Application

```bash
streamlit run main.py
```

---

# Workflow

```
User Opens Application
          │
          ▼
      Login Screen
          │
          ▼
Choose Exercise
          │
          ▼
 Webcam Starts
          │
          ▼
 Pose Detection
          │
          ▼
Exercise Detection
          │
          ▼
Rep Counting
          │
          ▼
Form Analysis
          │
          ▼
AI Coach Feedback
          │
          ▼
Workout Saved
```

---

# Dependencies

- Streamlit
- Streamlit WebRTC
- MediaPipe
- OpenCV
- Pandas
- Groq SDK
- gTTS
- python-dotenv

---

# Future Improvements

- User dashboard
- Workout plans
- Nutrition recommendations
- Multi-person tracking
- Calories estimation
- Exercise analytics
- Cloud database
- Mobile application
- Leaderboard
- Wearable device integration

---

# Contributing

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature-name
```

3. Commit your changes.

```bash
git commit -m "Added feature"
```

4. Push to your branch.

```bash
git push origin feature-name
```

5. Open a Pull Request.

---

# License

This project is intended for educational and research purposes.

---

# Acknowledgements

- Streamlit
- MediaPipe
- OpenCV
- Groq
- Google Text-to-Speech
- Python Community

---

# Author

**AI Gym Coach**

An intelligent fitness assistant that combines computer vision, artificial intelligence, and voice interaction to deliver a real-time personal training experience.
