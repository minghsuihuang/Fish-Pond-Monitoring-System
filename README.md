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

## Local Interface
Access the monitoring system locally via: [Fish Pond Monitoring System Interface](http://192.168.1.39:8123/fish-pond-monitoring-system)

## Installation Guide
1. Ensure both Raspberry Pi 4 and ESP8266 are equipped with the necessary hardware and drivers.
2. Connect the Raspberry Pi 4 to your router.
3. Connect the ESP8266 with the sensors and devices as per the system architecture diagram.

## Usage
- Configure and control the devices using ESP Home Assistant.
- Monitoring data will be displayed on the OLED screen and can be viewed and managed through the Home Assistant interface.

## ESPHome Configuration Examples
Below are configuration code snippets for the ESP32 Cam and ESP8266:

### ESP32 Cam Configuration
```yaml
esphome:
  name: fish-pond-cam-1
  friendly_name: FISH_POND_CAM_1

esp32:
  board: esp32dev
  framework:
    type: arduino

# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: "68zj+48tgPiazmKNTMXPhWWMedGRmI1dEDnx5Xkr3Qk="

ota:
  password: "93ef3ef97ba52a1803957cae96ca44ae"

wifi:
  ssid: "IOT_2.4G"
  password: "IOTEEB0202"

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "Fish-Pond-Cam-1 Fallback Hotspot"
    password: "LzG00XyfVqwf"

captive_portal:

esp32_camera:
  external_clock:
    pin: GPIO0
    frequency: 20MHz
  i2c_pins:
    sda: GPIO26
    scl: GPIO27
  data_pins: [GPIO5, GPIO18, GPIO19, GPIO21, GPIO36, GPIO39, GPIO34, GPIO35]
  vsync_pin: GPIO25
  href_pin: GPIO23
  pixel_clock_pin: GPIO22
  power_down_pin: GPIO32
  name: Camera01
