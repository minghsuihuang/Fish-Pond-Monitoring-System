# Fish-Pond-Monitoring-System
IOT Final Project

## Project Introduction
The Fish Pond Monitoring System is an IoT system designed for monitoring fish ponds, using a Raspberry Pi 4 and ESP8266 (Wemos D1 R2 board). This system employs various sensors and devices to monitor real-time environmental conditions of the pond, such as water quality, temperature, outdoor humidity and temperature, water level, and more. Data collection and control are facilitated through ESP Home Assistant.

## System Architecture
- **Central Controller**: Raspberry Pi 4 connected to a router, serving as the system's hub.
- **Sensors and Actuators**:
  - ESP8266 (Wemos D1 R2 board)
  - SG90 Servo Motor
  - LED Light Strip
  - ESP32 Cam
  - OLED Display
  - TDS Water Quality Sensor
  - Water Temperature Sensor
  - Outdoor Temperature and Humidity Sensor
  - Water Level Sensor
  - Water Pump

## Installation Guide
1. Ensure both Raspberry Pi 4 and ESP8266 are equipped with the necessary hardware and drivers.
2. Connect the Raspberry Pi 4 to your router.
3. Connect the ESP8266 with the sensors and devices as per the system architecture diagram.

## Usage
- Configure and control the devices using ESP Home Assistant.
- Monitoring data will be displayed on the OLED screen and can be viewed and managed through the Home Assistant interface.

## Code Examples
Here are some configuration code snippets for the ESP32 Cam and ESP8266:
```yaml
# Configuration for ESP32 Cam
esphome:
  name: fish-pond-cam-1
  ...
  # [Complete configuration code]

# Configuration for ESP8266
esphome:
  name: fish-pond
  ...
  # [Complete configuration code]
