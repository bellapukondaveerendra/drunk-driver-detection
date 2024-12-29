```
# Driver Drowsiness Detection System

## Overview
The **Driver Drowsiness Detection System** is a real-time application that uses computer vision and machine learning to monitor the driver's eyes and alert them if they are drowsy. This system aims to improve road safety by preventing accidents caused by driver fatigue.

---

## Features
- **Real-time Face and Eye Detection**: Detects the face and eyes of the driver using Haar Cascade Classifiers.
- **Eye State Classification**: Uses a Convolutional Neural Network (CNN) model to classify eye states as `Open` or `Closed`.
- **Drowsiness Score**: Maintains a score to determine the driver's drowsiness level based on eye closure duration.
- **Audio Alert**: Triggers an alarm sound when the driver is detected as drowsy.
- **Live Video Feed**: Processes the video feed from the camera in real-time.

---

## Requirements
### Libraries and Frameworks
- Python
- OpenCV
- Keras
- NumPy
- PyGame

### Additional Files
- Pre-trained CNN model: `models/cnncat2.h5`
- Haar Cascade files for face and eye detection:
  - `haarcascade_frontalface_alt.xml`
  - `haarcascade_lefteye_2splits.xml`
  - `haarcascade_righteye_2splits.xml`
- Alarm sound file: `alarm.wav`

---

## How It Works
1. **Initialization**:
   - Load the Haar Cascade Classifiers for face and eye detection.
   - Load the pre-trained CNN model for eye state classification.
   - Initialize an alarm system using PyGame.

2. **Real-time Processing**:
   - Capture video from the webcam.
   - Convert frames to grayscale for processing.
   - Detect faces and eyes in the frames using Haar Cascades.

3. **Eye State Prediction**:
   - Extract regions of interest (eyes) and preprocess them.
   - Classify the eye state (`Open` or `Closed`) using the CNN model.

4. **Drowsiness Detection**:
   - Maintain a score based on the duration of eye closure.
   - If the score exceeds a threshold, trigger an alarm and highlight the frame with a red border.

5. **Stopping the System**:
   - The system can be stopped by pressing the `q` key.

---

## Usage
1. Place the required Haar Cascade files, pre-trained CNN model, and alarm sound file in the project directory.
2. Run the Python script:
   ```bash
   python drowsiness_detection.py

```

1.  Ensure the webcam is connected and functioning properly.
2.  The system will start monitoring the driver's eyes and alert if drowsiness is detected.

* * * * *

Customization
-------------

-   **Threshold for Drowsiness Alert**: Adjust the `score` threshold (currently set at 5) to modify sensitivity.
-   **Alarm Sound**: Replace `alarm.wav` with your preferred sound file.
-   **Camera Input**: Modify the `cv2.VideoCapture(0)` line to use a different camera source.

* * * * *

Future Improvements
-------------------

-   Integrate head pose detection to enhance drowsiness detection.
-   Extend functionality for multiple drivers.
-   Deploy the system on mobile or edge devices for better portability.

* * * * *

License
-------

This project is open-source and can be modified or distributed under the terms of the MIT License.

```

Feel free to adapt or expand this file based on additional project details or requirements!

```
