
# Face Recognition Attendance System

A Python-based face recognition attendance system that identifies known faces through a webcam and automatically records their attendance in a CSV file.

## Overview

This project uses computer vision and facial recognition to detect faces in a live webcam feed. When a recognized person appears on camera, the system displays their name and records their attendance along with the current time.

Unknown faces are labeled as **“Unknown Person”** and are not added to the attendance record.

## Features

* Real-time face detection through a webcam
* Facial recognition using stored reference images
* Automatic attendance marking
* Attendance saved in a CSV file
* Prevents duplicate attendance entries during a session
* Labels unrecognized faces as “Unknown Person”
* Displays bounding boxes and names on the video feed

## Technologies Used

* Python
* OpenCV (`cv2`)
* NumPy
* `face_recognition` library
* CSV file handling
* Datetime module

## Project Structure

```text
Face-Recognition-Attendance-System/
│
├── Images/
│   ├── person1.jpg
│   ├── person2.jpg
│   └── ...
│
├── Attendance.csv
├── main.py
└── README.md
```

## How It Works

1. The program loads all images stored in the `Images` folder.
2. Each image is encoded using the `face_recognition` library.
3. The webcam captures live video frames.
4. Faces in each frame are detected and compared with the stored encodings.
5. When a match is found, the person’s name is displayed on screen.
6. The person’s name and attendance time are added to `Attendance.csv`.
7. Faces that do not match the known images are marked as **Unknown Person**.

## Installation

Install the required libraries:

```bash
pip install opencv-python numpy face-recognition
```

> Note: The `face_recognition` package may require `dlib`, which can sometimes need additional setup depending on your operating system.

## Usage

1. Add clear images of known people to the `Images` folder.
2. Name each image after the person it represents. For example:

```text
Images/
├── Ali.jpg
├── Ahmed.jpg
└── Sara.jpg
```

3. Create an `Attendance.csv` file in the project folder.
4. Run the program:

```bash
python main.py
```

5. Press the appropriate key or close the webcam window to stop the program.

## Attendance File Format

The attendance file records the name and time of each recognized person:

```text
Name, Time
Ali, 09:15:34
Sara, 09:18:02
```

## Possible Improvements

* Add dates along with attendance times
* Create a graphical user interface
* Store attendance in a database instead of a CSV file
* Add an admin panel for managing registered faces
* Improve recognition accuracy in low-light conditions
* Add a feature to export daily or weekly attendance reports
* Add liveness detection to reduce false recognition from photos

## Disclaimer

This project was created for learning purposes and demonstrates basic facial recognition and attendance automation. Facial-recognition systems should be used responsibly, with the knowledge and consent of the individuals whose images are included.
