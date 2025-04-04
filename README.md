# Real-Time Pose Detection and Exercise Tracking

### Project Overview
This project leverages MediaPipe and OpenCV to perform real-time pose detection and exercise tracking. The application detects human poses using a webcam feed and calculates the angle between specific body joints to track exercises, such as bicep curls. It visualizes the pose landmarks, calculates angles, and provides feedback on exercise performance, such as counting repetitions and detecting the exercise stage.

### Dependencies
OpenCV: For video capture and image processing.

MediaPipe: For pose detection and landmark extraction.

NumPy: For mathematical operations.


To install the dependencies, use the following command:
pip install mediapipe opencv-python numpy

### Key Components
1. Install and Import Dependencies
The initial step involves installing and importing the necessary libraries.

2. Real-Time Video Feed
A video feed is captured from the webcam and displayed using OpenCV's imshow function. The feed is shown in a window titled "Mediapipe Feed".

3. Pose Detection
MediaPipe's Pose model detects human pose landmarks in the video feed. The landmarks are then rendered on the video feed using MediaPipe’s drawing utilities.

4. Angle Calculation
Angles between specific joints (e.g., shoulder, elbow, wrist) are calculated to analyze the exercise form. The angle is computed using the arctangent function and visualized on the video feed.

5. Curl Counter
The application tracks the number of bicep curls performed. It determines the exercise stage (up or down) based on the angle between joints and updates the counter accordingly.


### Usage
Run the script to start the real-time pose detection and exercise tracking application. The application will display a video feed with pose landmarks and exercise metrics such as the number of repetitions and current stage of the exercise.

### Contributions
Feel free to contribute to the project by improving the pose detection accuracy, adding more exercise types, or optimizing the code. For any issues or suggestions, please open an issue in the repository.

