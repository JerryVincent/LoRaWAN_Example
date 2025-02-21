# ESP32 LoRaWAN Soil Moisture Monitoring

This project demonstrates how to use an ESP32 microcontroller with a LoRaWAN module to monitor soil moisture levels and transmit the data to a LoRaWAN network. The project uses the CayenneLPP format for encoding the data and the IBM LMIC framework for LoRaWAN communication.

## Table of Contents
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [LoRaWAN Configuration](#lorawan-configuration)
- [License](#license)

## Features
- **Soil Moisture Monitoring**: Reads soil moisture levels using an analog sensor.
- **LoRaWAN Communication**: Transmits soil moisture data to a LoRaWAN network.
- **CayenneLPP Format**: Encodes data in CayenneLPP format for easy integration with IoT platforms.
- **OTAA Join**: Uses Over-The-Air Activation (OTAA) to join the LoRaWAN network.

## Hardware Requirements
- ESP32 microcontroller with LoRaWAN module (e.g., SX1276)
- Soil moisture sensor
- Jumper wires
- Breadboard (optional)

## Software Requirements
- Arduino IDE
- ESP32 board package for Arduino IDE
- Libraries:
  - `SPI.h`
  - `lmic.h` (IBM LMIC framework)
  - `hal/hal.h`
  - `CayenneLPP.h`

## Installation
1. **Install Arduino IDE**: Download and install the Arduino IDE from [arduino.cc](https://www.arduino.cc/en/software).
2. **Install ESP32 Board Package**:
   - Open Arduino IDE, go to `File > Preferences`.
   - Add the following URL to the "Additional Boards Manager URLs" field:
     ```
     https://dl.espressif.com/dl/package_esp32_index.json
     ```
   - Go to `Tools > Board > Boards Manager`, search for `esp32`, and install the package.
3. **Install Required Libraries**:
   - Go to `Sketch > Include Library > Manage Libraries`.
   - Search for and install the following libraries:
     - `IBM LMIC framework`
     - `CayenneLPP`

## Configuration
1. **LoRaWAN Keys**:
   - Replace the `APPEUI`, `DEVEUI`, and `APPKEY` with your LoRaWAN credentials. These should be provided by your LoRaWAN network provider.
   - Ensure the `DEVEUI` and `APPEUI` are in little-endian format, and the `APPKEY` is in big-endian format.

2. **Soil Moisture Sensor Pin**:
   - Ensure the soil moisture sensor is connected to the correct pin (default is `3`).

3. **LoRaWAN Pin Mapping**:
   - Adjust the `lmic_pinmap` structure to match the pin configuration of your ESP32 and LoRaWAN module.

## Usage
1. **Upload the Code**:
   - Connect your ESP32 to your computer via USB.
   - Select the correct board and port in the Arduino IDE (`Tools > Board` and `Tools > Port`).
   - Upload the code to the ESP32.

2. **Monitor Serial Output**:
   - Open the Serial Monitor (`Tools > Serial Monitor`) to view the ESP32's output, including LoRaWAN join status and data transmission logs.

3. **Data Transmission**:
   - The ESP32 will read the soil moisture level and transmit it to the LoRaWAN network every 60 seconds (configurable via `TX_INTERVAL`).

## LoRaWAN Configuration
- **OTAA Join**: The device uses Over-The-Air Activation (OTAA) to join the LoRaWAN network. Ensure your network supports OTAA and that the `APPEUI`, `DEVEUI`, and `APPKEY` are correctly configured.
- **CayenneLPP Format**: The soil moisture data is encoded in CayenneLPP format, which is widely supported by IoT platforms.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to contribute to this project by submitting issues or pull requests. Happy coding! 🌱
