# Realtime-Drowsiness-Detection-with-yawn-and-Alart-system
This project implements a real-time drowsiness and yawn detection system using Python, OpenCV, and dlib. The system can alert the user when it detects signs of drowsiness or yawning.

## Features

- Real-time detection of drowsiness based on the Eye Aspect Ratio (EAR).
- Real-time detection of yawning based on the distance between the upper and lower lips.
- Audio alerts for both drowsiness and yawning.
- Option to use different webcam indices.

## Requirements

- Python 3.x
- OpenCV
- dlib
- imutils
- numpy
- scipy
- espeak (for audio alerts)

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/ImtiazAhammad/Realtime-Drowsiness-Detection-with-yawn-and-Alart-system.git
    cd drowsiness_yawn_detection
    ```

2. Install the required Python packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Download the shape predictor model and place it in the project directory:
    - [shape_predictor_68_face_landmarks.dat](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

4. Ensure `espeak` is installed on your system for audio alerts. For example, on Ubuntu:
    ```bash
    sudo apt-get install espeak

## Usage

To run the drowsiness and yawn detection, use the following command:
```bash
python drowsiness_yawn.py --webcam [webcam_index]
```
- Replace `[webcam_index]` with the index of your webcam (default is 0).

## Explanation

The script performs the following steps:

1. **Initialization**:
    - Load the face detector (`haarcascade_frontalface_default.xml`) and the shape predictor (`shape_predictor_68_face_landmarks.dat`).
    - Start the video stream.

2. **Frame Processing**:
    - Read frames from the video stream.
    - Convert the frame to grayscale.
    - Detect faces in the frame using the face detector.
    - For each detected face, determine the facial landmarks.
    - Compute the Eye Aspect Ratio (EAR) and lip distance.
    - Draw contours around the eyes and lips.

3. **Drowsiness Detection**:
    - If the EAR falls below the threshold for a sufficient number of frames, trigger the drowsiness alarm.

4. **Yawn Detection**:
    - If the lip distance exceeds the yawn threshold, trigger the yawn alarm.

## Configuration

- `EYE_AR_THRESH`: Threshold for the eye aspect ratio to determine drowsiness.
- `EYE_AR_CONSEC_FRAMES`: Number of consecutive frames the EAR must be below the threshold to trigger the drowsiness alarm.
- `YAWN_THRESH`: Threshold for the lip distance to determine yawning.

## Sample Output

![Sample Output](sample_output.png)

## Contributing

Feel free to submit issues and enhancement requests.

