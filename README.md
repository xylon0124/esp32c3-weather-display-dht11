# ESP32-C3 Weather Display with DHT11

A compact weather station using the ESP32-C3 SuperMini, DHT11 temperature and humidity sensor, and a 128×32 OLED display. Displays real-time readings with Wi-Fi capability for future IoT integration. Ideal for learning IoT, sensors, and microcontroller programming.

## Features

- **Real-time monitoring**: Displays current temperature and humidity readings
- **Compact design**: Uses the ESP32-C3 SuperMini microcontroller
- **Visual display**: 128×32 OLED display for clear readouts
- **Wi-Fi capable**: Built-in Wi-Fi for potential cloud integration and remote monitoring
- **Low power consumption**: Efficient DHT11 sensor for extended operation
- **Educational**: Perfect for learning IoT concepts, sensor integration, and embedded programming

## Hardware Requirements

- **ESP32-C3 SuperMini** - Compact development board with Wi-Fi and Bluetooth LE
- **DHT11 Sensor** - Temperature and humidity sensor
  - Temperature range: 0-50°C (±2°C accuracy)
  - Humidity range: 20-90% RH (±5% accuracy)
- **128×32 OLED Display** - I2C-based monochrome display
- **Breadboard and jumper wires** - For prototyping
- **USB-C cable** - For programming and power

## Software Requirements

- **Arduino IDE** (1.8.x or newer) or **PlatformIO**
- **ESP32 Board Support Package** for Arduino IDE
- **Required Libraries**:
  - Adafruit Unified Sensor
  - DHT sensor library
  - Adafruit SSD1306 (for OLED display)
  - Adafruit GFX Library

## Wiring Diagram

### DHT11 Sensor Connections
| DHT11 Pin | ESP32-C3 Pin |
|-----------|--------------|
| VCC       | 3.3V         |
| DATA      | GPIO4        |
| GND       | GND          |

### OLED Display Connections (I2C)
| OLED Pin  | ESP32-C3 Pin |
|-----------|--------------|
| VCC       | 3.3V         |
| GND       | GND          |
| SCL       | GPIO8 (SCL)  |
| SDA       | GPIO10 (SDA) |

*Note: Pin assignments may vary based on your specific board configuration. Adjust accordingly in the code.*

## Installation

### 1. Install Arduino IDE or PlatformIO

Download and install [Arduino IDE](https://www.arduino.cc/en/software) or [PlatformIO](https://platformio.org/).

### 2. Install ESP32 Board Support

**For Arduino IDE:**
1. Open Arduino IDE
2. Go to File → Preferences
3. Add the following URL to "Additional Board Manager URLs":
   ```
   https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
   ```
4. Go to Tools → Board → Boards Manager
5. Search for "esp32" and install "esp32 by Espressif Systems"

### 3. Install Required Libraries

**For Arduino IDE:**
1. Go to Sketch → Include Library → Manage Libraries
2. Search and install:
   - "DHT sensor library" by Adafruit
   - "Adafruit Unified Sensor" by Adafruit
   - "Adafruit SSD1306" by Adafruit
   - "Adafruit GFX Library" by Adafruit

**For PlatformIO:**
Add to your `platformio.ini`:
```ini
lib_deps = 
    adafruit/DHT sensor library
    adafruit/Adafruit Unified Sensor
    adafruit/Adafruit SSD1306
    adafruit/Adafruit GFX Library
```

### 4. Clone or Download This Repository

```bash
git clone https://github.com/xylon0124/esp32c3-weather-display-dht11.git
cd esp32c3-weather-display-dht11
```

### 5. Upload the Code

1. Connect your ESP32-C3 SuperMini to your computer via USB-C
2. Select the correct board: Tools → Board → ESP32 Arduino → ESP32C3 Dev Module
3. Select the correct port: Tools → Port → (your device port)
4. Click Upload

## Usage

Once the code is uploaded and the device is powered on:

1. The OLED display will initialize and show the startup screen
2. Temperature and humidity readings will be displayed in real-time
3. Readings are updated every few seconds
4. The display shows:
   - Temperature in Celsius (°C)
   - Relative Humidity as a percentage (%)

## Future Enhancements

This project has Wi-Fi capability built-in, enabling several potential improvements:

- **Cloud Integration**: Send data to IoT platforms like ThingSpeak, Blynk, or AWS IoT
- **Web Interface**: Create a local web server to view readings from any browser
- **MQTT Support**: Integrate with home automation systems (Home Assistant, OpenHAB)
- **Data Logging**: Store historical data for trend analysis
- **Alerts**: Send notifications when temperature/humidity exceeds thresholds
- **Battery Operation**: Add deep sleep mode for battery-powered deployment
- **Additional Sensors**: Expand with barometric pressure, light, or air quality sensors

## Troubleshooting

### Display not working
- Check I2C connections (SDA and SCL)
- Verify the display I2C address (usually 0x3C or 0x3D)
- Check power supply (3.3V)

### Sensor readings showing NaN or incorrect values
- Verify DHT11 connections
- Ensure proper power supply
- Check the data pin connection
- Add a 10kΩ pull-up resistor between DATA and VCC if needed

### Upload fails
- Press and hold the BOOT button while clicking Upload
- Check USB cable and drivers
- Try a different USB port

## Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Bence Kovács**

## Acknowledgments

- Adafruit for the excellent sensor and display libraries
- Espressif for the ESP32 platform
- The Arduino and PlatformIO communities

---

⭐ If you find this project helpful, please consider giving it a star!
