# ESP32 Setup Guide

This guide walks you through setting up your development environment for programming the ESP32 using PlatformIO and the ESP-IDF framework.

---

## Requirements
- **ESP32 Development Board** (e.g., ESP32-WROOM-32)
- **USB Cable** (ensure it supports both power and data transfer)
- **Computer** with one of the following operating systems:
  - Windows
  - macOS
  - Linux
- **Visual Studio Code** with PlatformIO extension installed

---

## Step-by-Step Instructions

### 1. Install Visual Studio Code
1. Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com/).
2. Install it on your computer following the provided instructions for your operating system.

### 2. Install PlatformIO Extension
1. Open Visual Studio Code.
2. Go to the Extensions Marketplace (click the square icon on the left sidebar or press `Ctrl+Shift+X`).
3. Search for `PlatformIO IDE` and click **Install**.

### 3. Install ESP-IDF Framework
1. Open the PlatformIO Home screen by clicking the alien icon in the left sidebar.
2. Go to **Platforms** > **Embedded** > Search for **Espressif 32**.
3. Click **Install** to add the ESP32 platform and ESP-IDF framework to your environment.

### 4. Create a New Project
1. In PlatformIO Home, click **New Project**.
2. Fill in the details:
   - **Project Name**: Enter your desired name (e.g., "ESP32-Blink").
   - **Board**: Select your ESP32 board (e.g., `esp32dev` for ESP32-WROOM-32).
   - **Framework**: Choose `ESP-IDF`.
3. Click **Finish** to create the project.

### 5. Connect Your ESP32
1. Use a USB cable to connect your ESP32 board to your computer.
2. Verify the connection:
   - On Windows: Check the Device Manager for a new COM port.
   - On macOS/Linux: Run `ls /dev/tty*` to identify the connected device.

### 6. Select the Correct Serial Port
1. Open the `platformio.ini` file in your project.
2. Add or edit the following line:
   ```ini
   monitor_port = <your_serial_port>
3. Replace <your_serial_port> with the name of your port (e.g., COM3 on Windows or /dev/ttyUSB0 on Linux).

### 7. Test the Setup
1. Copy and paste a sample program (e.g., Blink) into the main.c file in your project.
2. Build the project:

```bash
idf.py build
```

3. Flash the program to your ESP32:

```bash
idf.py flash
```

4. Monitor the serial output to verify everything works:

```bash
idf.py monitor
```

## Troubleshooting

### **1. My ESP32 is not detected by my computer.
- Verify that your USB cable supports data transfer.
- Ensure drivers for the ESP32 are installed:
  - For Windows, install the CP210x or CH340 drivers.
  - For macOS/Linux, the drivers are usually pre-installed.
### **2. I get build errors when compiling my project.
- Ensure you selected the correct framework (ESP-IDF) and board in your project setup.
- Check that all required libraries are installed. PlatformIO should manage this automatically.
### **3. My program flashes successfully, but nothing happens.
- Confirm the program logic is correct.
- Double-check the GPIO connections.
- Verify the ESP32 board is powered and functional.
### **4. The serial monitor shows garbled output.
Ensure the baud rate in your serial monitor matches the baud rate configured in your project (default: 115200).
