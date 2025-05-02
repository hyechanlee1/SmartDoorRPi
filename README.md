# 🔐 Smart Door

A smart, keyless door system using Raspberry Pi, facial recognition, and a mobile app for secure access.

![Smart Door Hardware Setup](/diagrams/wirings.jpg)

## 🚀 What It Does

- Detects motion with a sensor.
- Uses facial recognition to identify people.
- Sends unlock requests to a phone app.
- Opens the door only after confirmation.
- Lets users register new faces using a button and app.

## 🧰 Hardware Used

- Raspberry Pi
- PiCamera
- PIR Motion Sensor
- 2 Servo Motors (Lock + Door)
- 3 LEDs (Red, Green, Yellow)
- 1 Push Button
- Resistors and Wires

## 💻 Software Used

- Python
- OpenCV (image handling)
- face-recognition (facial recognition)
- imutils (image utilities)
- paho-mqtt (for app communication)
- pigpio and gpiozero (for hardware control)

## 🔧 How It Works

1. Motion triggers the camera.
2. If a known face is detected:
   - Sends a confirmation request to your phone.
   - Unlocks and opens the door if confirmed.
3. Unknown faces trigger alerts only.
4. New users can register by pressing a button and confirming from the app.

## 🔒 Security

- Runs facial recognition locally.
- Communicates over MQTT with username/password.
- No cloud storage—everything stays on the Pi.

## 📲 MQTT Topics

- `hl63/door_control`: Receives commands from the app.
- `hl63/door_status`: Sends door status.
- `hl63/door_alert`: Sends alerts (recognized face, training done, etc.).

## ✅ Setup

1. Wire components.
2. Install libraries:  
   `pip install opencv-python face-recognition imutils paho-mqtt gpiozero`
3. Run with:  
   `python3 smart_door.py`

## 👥 Authors

- Hye Chan Lee  
- Clive Amoh  
CS 326 - Calvin University
