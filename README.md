# 🌡️ ESP32-C3 DHT11 + OLED Environmental Monitor

A lightweight ESP32-C3 firmware that reads temperature and humidity from a **DHT11 sensor**  
and displays the values on a **128×32 I²C OLED** (SSD1306 driver).  
Designed for minimal power consumption and easy integration with future MQTT or Node-RED systems.

---

## ⚙️ Features
- ✅ Reads temperature (°C) and humidity (%) using DHT11 sensor  
- ✅ Displays data on a 128×32 I²C OLED screen (SSD1306)  
- ✅ Clean, modular Arduino C++ code  
- ✅ Compatible with **ESP32-C3 DevKit**, **Geekble Mini ESP32-C3**, etc.  
- ⚡ Low power, headless-ready design (no serial output needed after init)

---

## 🧩 Hardware Setup

| Component | ESP32-C3 Pin | Notes |
|------------|--------------|-------|
| DHT11 DATA | GPIO 10 | 10 kΩ pull-up resistor to 3.3 V recommended |
| OLED SDA | GPIO 8 | Default I²C SDA |
| OLED SCL | GPIO 9 | Default I²C SCL |
| VCC (OLED/DHT) | 3.3 V | Do **not** use 5 V |
| GND | GND | Common ground |

---

## 🧠 Software Requirements
Install via Arduino Library Manager:
- #include "DHT.h"
- #include <Wire.h>
- #include <Adafruit_GFX.h>
- #include <Adafruit_SSD1306.h>


