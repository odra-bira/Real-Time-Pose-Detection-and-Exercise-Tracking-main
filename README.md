# Real-Time Pose Detection & Exercise Tracking

A webcam-based computer vision notebook that detects body landmarks, calculates the left elbow angle, and counts bicep curls with MediaPipe, OpenCV, and NumPy.

[Portfolio](https://odra-bira.github.io/) · [Open notebook](notebooks/pose_tracking.ipynb)

## Features

- Live webcam capture and skeleton overlay.
- Shoulder–elbow–wrist angle calculation.
- A two-state repetition counter: arm extension above 160° sets the down state; flexion below 30° then counts a repetition.
- On-screen angle, repetition count, and movement stage.

## Run locally

Use a computer with a webcam and a graphical desktop. Remote/headless notebook sessions cannot directly display the OpenCV windows or access your local camera.

```bash
git clone https://github.com/odra-bira/Real-Time-Pose-Detection-and-Exercise-Tracking-main.git
cd Real-Time-Pose-Detection-and-Exercise-Tracking-main
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter notebook notebooks/pose_tracking.ipynb
```

On Windows, activate with `.venv\Scripts\activate`.

Run the notebook sequentially. Each camera-loop cell opens its own window; focus that window and press **q** to finish the cell before continuing. Allow camera access when prompted.

The notebook uses the legacy `mediapipe.solutions.pose` API. Install a compatible MediaPipe release that exposes this API; the dependency file does not guarantee compatibility with every release.

## How counting works

The angle at the elbow is computed from three 2D landmark coordinates. A repetition is recorded only after the arm moves from the extended state to the flexed state. Fixed thresholds make the logic easy to inspect, but do not measure exercise quality.

## Repository guide

| Path | Purpose |
| --- | --- |
| `notebooks/pose_tracking.ipynb` | Step-by-step pose detection and curl counting |
| `requirements.txt` | Direct dependencies |
| `.gitignore` | Excludes generated notebook and environment files |

## Limitations

- Tracks the left arm with fixed thresholds.
- Sensitive to camera placement, lighting, occlusion, and landmark quality.
- Does not include a labeled benchmark or verified accuracy/FPS measurements.
- Demonstrates pose estimation and counting, not medical or professional fitness assessment.

## Author

Odra Bira · [Portfolio](https://odra-bira.github.io/)
