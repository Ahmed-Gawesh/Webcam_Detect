# Real-Time Object Detection with YOLOv12
Overview
This project implements real-time object detection using the YOLOv12 model with a webcam or video file as input. It detects objects from a predefined list of 80 classes (e.g., person, car, dog) and displays bounding boxes with class names and confidence scores on the video feed.
Features

Real-time object detection using YOLOv12.
Supports webcam input or pre-recorded video files.
Displays bounding boxes with class labels and confidence scores.
Uses cvzone for enhanced bounding box visualization.
Configurable video resolution (default: 1280x720).

# Requirements

Python 3.8+
OpenCV (cv2)
Ultralytics YOLO (yolo)
cvzone
numpy
math

Installation


# Install dependencies:
pip install opencv-python ultralytics cvzone numpy


Download the YOLOv12 weights (weights_yolo12n.pt) and place them in the project directory. You can download the weights from the Ultralytics YOLO repository or train your own model.


# Usage

Ensure your webcam is connected or you have a video file (e.g., people.mp4) in the project directory.
Run the script:python object_detection.py


The script will open a window displaying the video feed with detected objects, their class names, and confidence scores.

Input Options

Webcam: The script defaults to using the webcam (cv2.VideoCapture(0)).
Video File: Uncomment the line cap=cv2.VideoCapture('people.mp4') and comment out the webcam line to use a video file.

Controls

Press any key to exit the video feed window.

# Code Explanation

Video Capture: Uses OpenCV to capture video from a webcam or file.
YOLO Model: Loads the YOLOv12 model with pre-trained weights (weights_yolo12n.pt).
Object Detection: Processes each frame, detects objects, and draws bounding boxes with cvzone.cornerRect.
Annotations: Displays class names and confidence scores using cvzone.putTextRect.
Class List: Supports 80 object classes (e.g., person, car, dog) defined in classNames.

# Example Output
The output window shows the video feed with:

Rectangular bounding boxes around detected objects.
Class names (e.g., "person", "car") and confidence scores (e.g., "0.92") above each box.

# Notes

Ensure the weights_yolo12n.pt file is in the correct directory.
Adjust the resolution (cap.set(3, 1280), cap.set(4, 720)) as needed for your hardware.
For better performance, use a GPU-enabled environment if available.


