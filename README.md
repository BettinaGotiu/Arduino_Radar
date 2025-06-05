# Arduino Radar Project

## Overview

This project implements a simple radar system using an Arduino microcontroller, an ultrasonic sensor, a servo motor, and a Processing-based UI. The radar visualizes the distance and angle of detected objects in real-time. 

## Purpose

The purpose of this project is to demonstrate how to build a DIY radar system using affordable components and to visualize the sensor data on a computer. The system scans its surroundings by rotating an ultrasonic sensor and displays the detected distances on a radar-like interface.

## Project Structure

- **Arduino_Radar.ino**: Arduino (C++) source code for controlling the servo motor and ultrasonic sensor, and sending data over serial.
- **Arduino_Radar.pde**: Processing source code for receiving the serial data from Arduino and rendering the radar visualization on the computer.

## How It Works

### Hardware

- The Arduino is connected to:
  - A **servo motor** that sweeps the ultrasonic sensor across a set range of angles (15° to 165°).
  - An **ultrasonic distance sensor** (trigger and echo pins) to measure the distance to objects.
- The Arduino sends angle and distance data via serial communication to the PC.

### Software

- The **Arduino code** controls the servo and sensor, and formats the output for the Processing application.
- The **Processing application** reads the serial data, parses the angle and distance, and draws a real-time radar display representing the detected objects.

## Demo

A demonstration of the project can be found in the file **Functionare.mp4**.  
This video shows the radar system in action. When the system detects objects, the corresponding area is highlighted on the graphical interface, making it easy to visualize object positions and distances in real-time.

## File Details

### Arduino_Radar.ino

- **Purpose**: This file contains the Arduino sketch that:
  - Rotates the servo motor from 15° to 165° and back.
  - Triggers the ultrasonic sensor to measure distance at each angle.
  - Sends angle and distance data as formatted serial output for the Processing app.
- **Key Features**:
  - Accurate distance calculation using pulse duration and speed of sound.
  - Serial communication protocol: `angle,distance.` (e.g., `45,30.`).

### Arduino_Radar.pde

- **Purpose**: This Processing sketch provides the graphical user interface for the radar.
- **What it does**:
  - Reads serial data from the Arduino.
  - Parses the angle and distance information.
  - Visually displays a radar sweep, plotting detected objects and their angles/distances.
  - Shows real-time status messages ("In Range"/"Out of Range"), angle, and distance.
- **Key Features**:
  - Customizable and visually appealing radar display.
  - Real-time updates as the Arduino scans.

## Getting Started

### Requirements

- Arduino Uno or compatible board
- Ultrasonic distance sensor (e.g., HC-SR04)
- Servo motor
- Jumper wires and breadboard
- USB cable for serial connection


### Steps

1. **Upload Arduino_Radar.ino** to your Arduino using the Arduino IDE.
2. **Connect hardware** as specified in the Arduino sketch.
3. **Open Arduino_Radar.pde** in Processing and run the sketch.
4. **Set the correct serial port** in the Processing sketch (default is `"COM3"`, change as needed for your system).
5. Observe the radar sweep and object detection visualization on your screen.
