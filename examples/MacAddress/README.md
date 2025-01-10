# ESP32 MAC Address Retrieval Example

This project demonstrates how to retrieve and display the ESP32's MAC address using the ESP-IDF framework.

## Features
- Initializes the ESP32's NVS (Non-Volatile Storage) and Wi-Fi stack.
- Retrieves the MAC address for the ESP32's station interface.
- Prints the MAC address to the serial monitor in a human-readable format.

## Code Overview
The main program performs the following steps:
1. Initializes the ESP32's NVS flash to ensure proper storage operations.
2. Sets up the Wi-Fi stack in station mode.
3. Retrieves the device's MAC address for the Wi-Fi station interface.
4. Outputs the MAC address to the serial monitor in the format `XX:XX:XX:XX:XX:XX`.

### Example Output
```
MAC Address: 24:6F:28:1A:2B:3C
```

## Requirements
- **ESP32 Development Board**
- **ESP-IDF Framework**
- **Serial Monitor** (e.g., PlatformIO Serial Monitor, minicom, or PuTTY)

## Usage
1. Clone this repository and open the project in an ESP-IDF-compatible IDE (e.g., Visual Studio Code with PlatformIO).
2. Build and flash the program to your ESP32.
3. Open the serial monitor to view the output, (remember you can do this by clciking the plug icon in the bottom ribbon).

## File Breakdown
- `main.c`: Contains the program logic for initializing the ESP32 and retrieving the MAC address.
- `platformio.ini`: Specifies the platform, board, framework, and other configuration details.

## How to Run
1. Connect your ESP32 to your computer using a USB cable.
2. Ensure the correct serial port is selected in your environment.
3. Build, flash, and monitor the project using the following command:
   ```bash
   idf.py build flash monitor
   ```
4. Observe the MAC address output in the serial monitor.

## Troubleshooting
- If the MAC address does not appear, verify that the serial monitor is configured for the correct baud rate (default: 115200).
- Check that your ESP32 is properly connected and powered.
- Ensure the ESP-IDF environment is correctly set up and your ESP32 drivers are installed.

## Notes
- The MAC address is unique to each ESP32 device and can be used for identifying the device in a network.
- Modifications to the code can allow retrieval of the MAC address for other Wi-Fi interfaces, such as the AP (Access Point) mode, by changing the argument in `esp_wifi_get_mac`.