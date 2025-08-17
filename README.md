# Drowsy Driver Alert System

### Overview
This project implements a real-time drowsiness detection system that alerts drivers when signs of fatigue are detected. Using computer vision and facial landmark analysis, it monitors the driver’s eyes and classifies states as Active, Drowsy, or Sleeping. If drowsiness or sleep is detected for consecutive frames, an audible alarm is triggered to prevent accidents.

### Features
1. Real-time face and eye detection from webcam video.
2. 68-point dlib facial landmark predictor to track eye movement.
3. Blink ratio (EAR-like metric) to detect open, drowsy, and closed eyes.
4. Audible alerts when the driver is drowsy or sleeping.
5. Live video feed overlay with eye status and landmarks.

### Tech Stack
Python
OpenCV – video processing
dlib – face detection and 68-point landmark predictor
imutils, NumPy, SciPy – numerical and image utilities
playsound – audio alerts

### How It Works
1. Capture video frames via OpenCV.
2. Detect faces using dlib’s HOG + Linear SVM detector.
3. Extract eye landmarks from the 68-point model.
4. Compute the eye aspect ratio (EAR):
    Eyes open → Active
    Eyes slightly closed → Drowsy
    Eyes closed for several frames → Sleeping
5. Trigger audio alarms for Drowsy/Sleeping states.
