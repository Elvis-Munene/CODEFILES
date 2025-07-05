# 🌡️💡 Smart Environmental Control Systems using ESP32

This repository contains two IoT-based automation projects developed using the ESP32 microcontroller. Each project connects to a cloud platform, enabling real-time monitoring and remote control through secure HTTP communication.

---

## 📦 Projects Overview

### 1. Temperature & Humidity Monitoring with Fan Control

An intelligent environmental monitoring system that:

- Reads room temperature and humidity using a **DHT22** sensor.
- Sends the data to a remote cloud platform for live monitoring.
- Receives user-defined thresholds from the platform to control a **fan**.
- Displays real-time readings on an **OLED screen**.

**💡 Use Case:** Ideal for smart homes, greenhouses, classrooms, or office environments requiring automated temperature regulation.

### 2. SmartLights Control System

A smart lighting solution that:

- Toggles an **LED** ON or OFF based on commands from a web platform.
- Supports blinking functionality based on user-defined intervals.
- Allows scheduling of LED operations through platform-based timers.

**💡 Use Case:** Home and office lighting systems that benefit from automation, remote control, or timed operation.

---

## 🛠️ Common Tech Stack

- **Microcontroller:** ESP32
- **Communication:** Wi-Fi + HTTPS
- **Cloud Platform:** Custom API-enabled backend
- **Programming Language:** Arduino C++
- **Core Libraries:**
  - `WiFi.h`, `HTTPClient.h`, `WiFiClientSecure.h`
  - `Arduino_JSON.h`
  - `Adafruit_SSD1306` & `Adafruit_GFX` (for OLED display)
  - `DHT Sensor Library`

---

## 🧰 Hardware Components

| Component              | Purpose                                  |
|------------------------|-------------------------------------------|
| ESP32                  | Core microcontroller                      |
| DHT22 Sensor           | Measures temperature & humidity           |
| SSD1306 OLED Display   | Displays real-time data locally           |
| Fan                    | Actuated based on temperature thresholds  |
| LED                    | Controlled remotely or via schedule       |
| Wi-Fi                  | Enables platform connectivity             |
| Power Supply + Wires   | Circuit operation and connections         |

---

## 📌 Pin Configuration

| Pin Name           | GPIO Pin |
|--------------------|----------|
| DHT_PIN            | 7        |
| ONBOARD_LED_PIN    | 13       |
| INA_PIN (Fan)      | 38       |
| INB_PIN (Fan)      | 35       |
| OLED I2C_SCL       | 2        |
| OLED I2C_SDA       | 42       |
| Additional Pins    | See `pin_configurations.h` for full list |

---

## ⚙️ Setup Instructions

### 🔑 1. Secrets Configuration

Create a `secrets.h` file and add:

```cpp
#define SSID "your_wifi_ssid"
#define PASSWORD "your_wifi_password"
#define apiKeyValue "your_api_key"
#define server_url "https://your-platform.com/api"
