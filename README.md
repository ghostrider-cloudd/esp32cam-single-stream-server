# ESP32-CAM Single-Client Video Streamer

A simple and lightweight **ESP32-CAM video streaming server** that streams live video over **Wi-Fi** to a **single connected client**.  
Built for low-latency, stable performance, and minimal resource usage.  
Perfect for DIY IoT cameras, robotics, FPV, and embedded vision applications.

---

## 🚀 Features

- 📷 **Live MJPEG/HTTP video streaming**
- 👤 **Single-client optimized** for stable performance  
- ⚡ Very **low latency** and minimal RAM usage  
- 🌐 Works in **Wi-Fi STA/AP mode**  
- 🎛 Supports resolution and JPEG quality control  
- 🧩 Designed for **ESP32-CAM (AI Thinker)**  
- 🛠 Uses Arduino framework (easy to modify)

---

## 📦 Requirements

- ESP32-CAM (AI Thinker) or similar module  
- FTDI / USB-TTL programmer  
- Arduino IDE or PlatformIO  
- ESP32 board package installed  

---

## 🔧 Installation & Setup

1. Install ESP32 board package in Arduino IDE  
   - *File → Preferences → Additional Boards URL:*  
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```

2. Select the board:  
   **Tools → Board → ESP32 Arduino → AI Thinker ESP32-CAM**

3. Connect your ESP32-CAM via FTDI programmer:
   - **IO0 → GND** (flash mode)
   - **5V → 5V**
   - **GND → GND**
   - **U0R → TX**
   - **U0T → RX**

4. Flash the firmware  
5. Open the **Serial Monitor** (115200 baud) to get the camera’s IP address  

---

## 🌐 Usage

Open the streaming URL in your browser or VLC:

http://<your-ip-address>/stream

css
Copy code

For a single snapshot:

http://<your-ip-address>/capture

yaml
Copy code

> ⚠️ *Since this version is designed for one client only, connecting a second viewer may pause or reset the stream.*

---

## 📺 Stream Access

Default endpoints (may vary depending on your code):

- **Video stream:**  
/stream

markdown
Copy code
- **Snapshot:**  
/capture

yaml
Copy code

---

## 🛠 Configuration

You can customize settings in the source code:

### Camera settings:
```cpp
config.frame_size = FRAMESIZE_QVGA;   // Resolution
config.jpeg_quality = 12;             // Quality (lower = better quality)
config.fb_count = 1;                  // Single frame buffer for stability
Wi-Fi Setup:
cpp
Copy code
const char* ssid = "YOUR_WIFI";
const char* password = "YOUR_PASSWORD";
