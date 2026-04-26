# 🚗 Autonomous Navigation Car
📌 Overview

The Autonomous Navigation Car is an embedded systems project developed for the Microprocessor & Interfacing Lab (CSE 238).
This project demonstrates a smart vehicle capable of navigating its environment automatically while avoiding obstacles without human intervention.

🎯 Objective

The goal of this project is to design and implement a microcontroller-based system that integrates sensors, actuators, and control logic to achieve autonomous navigation.

⚙️ Features
🚀 Autonomous forward movement
📡 Obstacle detection using ultrasonic sensor
🔄 Left-right environmental scanning using servo motor
🧠 Real-time decision making (forward, stop, reverse, turn)
⚡ 4WD motor control using motor driver
🧩 Components Used
Arduino Uno (ATmega328P)
HC-SR04 Ultrasonic Sensor
SG90 Servo Motor
L293D Motor Driver Shield
4 DC Gear Motors (4WD chassis)
2 × 18650 Li-ion Batteries
🔌 Pin Configuration
Component	Pin Connection	Function
HC-SR04 Trig	A0	Sends ultrasonic signal
HC-SR04 Echo	A1	Receives reflected signal
Servo Motor	Pin 10	Rotates sensor
DC Motors	M1–M4	Drives wheels
🧠 Working Principle

The system operates using the ultrasonic time-of-flight principle:

The sensor sends an ultrasonic pulse
The echo is received after reflecting from an object
Distance is calculated using time delay
If an obstacle is detected within a threshold (≈20 cm):
Car stops
Moves backward
Scans left and right
Chooses the clearer path
The car resumes forward motion
🔄 Algorithm
Initialize motors and servo (center position)
Continuously measure forward distance
If distance < threshold:
Stop → Reverse
Scan right and left
Turn towards greater distance
Else:
Move forward
Repeat loop
💻 Code

Main libraries used:

AFMotor.h
NewPing.h
Servo.h

Core functionalities:

Distance measurement
Servo-based scanning
Motor control (forward, backward, turning)
📊 Results
Successfully avoids obstacles in simple environments
Performs autonomous navigation with basic decision-making
Works best with solid, flat obstacles
