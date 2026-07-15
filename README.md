# Real-Time Face Detection using OpenCV

A simple Python project that uses OpenCV's Haar Cascade classifier to detect human faces in real time through a webcam feed. Detected faces are highlighted with bounding boxes, labeled, and counted live on screen.

## Features

- Real-time face detection using your webcam
- Grayscale conversion with histogram equalization for better detection accuracy in varying lighting conditions
- Bounding boxes and labels drawn around detected faces
- Live face count displayed on screen
- Adjustable detection parameters (scale factor, minimum neighbors, size limits)

## Demo

The application opens a live webcam window. Each detected face is outlined in green with a "Face" label above it, and the total number of faces currently in frame is shown in the top-left corner.

## Requirements

- Python 3.x
- OpenCV (`opencv-python`)

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/RahulMahawar310/face_recognition.git
   cd face_recognition
   ```

2. Install the required dependency:
   ```bash
   pip install opencv-python
   ```

## Usage

Run the script:
```bash
python face_recognition.py
```

- A window titled **"Face Detection"** will open showing your webcam feed with detected faces highlighted.
- Press **`a`** to quit the application.

## How It Works

1. **Capture video** from the default webcam (`cv2.VideoCapture(0)`).
2. **Convert each frame to grayscale** and apply histogram equalization to improve contrast, which helps the classifier perform better under different lighting conditions.
3. **Detect faces** using OpenCV's pre-trained `haarcascade_frontalface_default.xml` classifier via `detectMultiScale`, tuned with:
   - `scaleFactor=1.3` — how much the image size is reduced at each image scale
   - `minNeighbors=8` — how many neighbors each candidate rectangle should have to retain it (higher = fewer false positives)
   - `minSize=(80, 80)` / `maxSize=(400, 400)` — ignores faces that are too small or too large to be valid
4. **Draw bounding boxes and labels** around each detected face and display a running face count.
5. **Exit** the loop and release the camera when the `a` key is pressed.

## Project Structure

```
.
├── face_recognition.py   # Main script
└── README.md
```

## Possible Improvements

- Add face recognition (identifying specific individuals) using `face_recognition` or a deep learning model
- Save snapshots of detected faces
- Support detection from video files or images, not just live webcam feed
- Replace Haar Cascade with a more accurate DNN-based face detector (e.g., OpenCV's `dnn` module or MTCNN)

## License

This project is open source and available under the [MIT License].
