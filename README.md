AIOT Smart Mask Detection & Temperature Screening System

A real-time Edge AI + IoT system built using Raspberry Pi, TensorFlow, OpenCV, and multiple sensors to detect face masks and automatically screen a person’s temperature before granting access.

This project integrates computer vision, deep learning, temperature sensing, GPIO automation, and servo-controlled access gates.

Features

Real-time face detection using OpenCV DNN

Mask vs No-Mask classification using a TensorFlow (MobileNetV2) model

Contactless temperature measurement using MLX90614 IR sensor

Servo-controlled gate that opens automatically on verification

Alert system with buzzer + LEDs

LCD display for user instructions and feedback

Fully optimized for Raspberry Pi 3/4

Modular, expandable codebase

Hardware Used
Component	Purpose
Raspberry Pi 3/4	Main controller
Pi Camera / USB Webcam	Vision input
MLX90614 IR Temperature Sensor	Contactless temperature
Servo Motor	Gate opening
LEDs (Normal & Alert)	Status indicators
Buzzer	Audio alerts
LCD Display (16×2)	User information
Breadboard & Wires	Circuit connections

Software & Libraries
Python 3
OpenCV
TensorFlow / Keras
MobileNetV2
imutils
gpiozero / RPi.GPIO
adafruit_mlx90614
rpi_lcd


Project Structure
AIOT_Project/
│── main.py
│── final_model.keras
│── face_detector/
│     ├── deploy.prototxt
│     ├── res10_300x300_ssd_iter_140000.caffemodel
│── requirements.txt
│── README.md

Installation
Clone the Repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO

Install Dependencies
pip install -r requirements.txt


Or manually install:

pip install tensorflow opencv-python imutils adafruit-circuitpython-mlx90614 rpi_lcd gpiozero

How It Works
Camera captures live video.
Face is detected using OpenCV’s Caffe-based model.
MobileNetV2 mask classifier predicts:
Mask
No Mask
If Mask:
LCD shows “Scan Temperature
IR sensor reads temperature
If temperature < safe threshold → Gate opens
Else → Alert LED + buzzer

If No Mask:
Buzzer aler
Red LED turns on
Gate stays locke

Run the Program
python3 main.py

Press Q in the window (or stop the program on Pi) to exit.

Demo (optional section)
You can add images/videos later:
/demo/
   ├── demo1.jpg
   ├── demo2.jpg
   └── video.mp4

Safety Threshold
Temperature > 95°F → Person flagged
Mask probability > 0.50 → Acceptable
You can tweak these in main.py.
Future Improvements
Add IR proximity sensor for auto-start
Firebase / Google Sheets logs
YOLO-based face detection
Deploy gateway logs via Flask API
Add MQTT + Cloud Dashboard

Author

Abhaya Sahoo
AIOT Engineer | IoT + ML Practitioner
