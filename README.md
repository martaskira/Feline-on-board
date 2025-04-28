# Feline-On-Board (FOB): Bluetooth Cat Proximity Alert System

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Hardware & Technology](#hardware--technology)
- [Prototypes](#prototypes)
- [How It Works](#how-it-works)
- [Setup & Usage](#setup--usage)
- [Demonstration](#demonstration)
- [Images](#images)
- [Limitations & Future Work](#limitations--future-work)
- [Reflections](#reflections)
- [Inspiration & Related Work](#inspiration--related-work)
- [License](#license)

---

## Project Overview

**Feline-On-Board (FOB)** is a wearable Bluetooth beacon system for outdoor pet cats. The device sits on a collar or harness and alerts owners when their cat is near the home, making it easier to know when to let the cat inside. The system uses a BLE beacon (transmitter) on the cat and a scanner (receiver) at home, providing both visual (display) and physical (LED) notifications when the cat is in proximity.

---

## Features

1. **Wearable BLE Beacon:** Small, waterproofed beacon attaches to a cat’s collar or harness.
2. **Home Scanner:** BLE scanner with TFT display and LED notification.
3. **Real-Time Alerts:** Notifies owner when the cat is within a few meters of the home.
4. **Visual Feedback:** TFT display shows beacon name and signal strength.
5. **Physical Feedback:** LED lights up when the cat is close.
6. **Portable Power:** Beacon can be powered by button batteries or a portable charger.
7. **Open Source Code:** Arduino-based code for both beacon and scanner provided.

---

## Hardware & Technology

- **Cat Beacon:**
  - Adafruit ESP32-S3 QT Py board (iBeacon broadcaster)
  - Powered by button batteries or portable charger
  - Waterproofed with silicone-lined case

- **Home Scanner:**
  - Adafruit ESP32-S3 Feather board with TFT display and LED
  - Powered by 3x AA batteries
  - BLE scanner code for iBeacon/Eddystone detection

- **Other:**
  - Custom enclosures for collar/harness integration
  - Optional: Battery holders, jumper wires, silicone lining

---

## Prototypes

- **Prototype 1:**  
  Cat collar with QT Py board and button batteries for minimal weight and disturbance to the cat.

- **Prototype 2:**  
  Harness with Feather board and AA batteries for situations where a smaller board/battery is unavailable.

- **Final Demo:**  
  QT Py beacon powered by a portable charger for reliability, Feather scanner with TFT and LED at home.

---

## How It Works

1. **Beacon Setup:**  
   The QT Py board broadcasts a unique BLE iBeacon signal with the device name "Cat_Beacon".

2. **Scanner Operation:**  
   The Feather board continuously scans for BLE beacons, displaying the beacon name and signal strength (RSSI) on the TFT display.

3. **Proximity Notification:**  
   When the beacon is within a set signal strength (e.g., RSSI > -65 dBm), the scanner lights up a red LED to alert the owner.

4. **Visual Output:**  
   The TFT display updates in real time, showing the beacon’s presence and distance estimation.

---

## Setup & Usage

### 1. Hardware Assembly

- Assemble the QT Py board with batteries or portable charger in a waterproofed case for the collar/harness.
- Assemble the Feather board with TFT display and LED, powered by AA batteries.

### 2. Flash the Code

- Upload the **BLE Beacon** code to the QT Py board (see `BLE_Server.ino`).
- Upload the **BLE Scanner** code to the Feather board (see `Scanner_TFT_Display.ino`).

### 3. Operation

- Attach the beacon to your cat’s collar or harness.
- Place the scanner inside your home near the door.
- When the cat approaches, the scanner will display the beacon info and light up the LED.

---

## Demonstration

- **Scenario:**  
  Owner is working at home. When the cat approaches the door, the scanner detects the beacon and lights up the LED, prompting the owner to let the cat inside.

- **Video Demo:**  
  (Add link to video demonstration if available.)

---

## Images

| Image | Description |
|-------|-------------|
| ![Collar Prototype](path/to/collar_prototype.jpg) | Prototype of cat collar with QT Py board and button batteries. |
| ![Harness Prototype](path/to/harness_prototype.jpg) | Prototype of cat harness with Feather board and AA batteries. |
| ![Collar with Feather Board](path/to/collar_with_featherboard.jpg) | IRL image: collar prototype with Feather board installed. |
| ![LED On](path/to/led_on.jpg) | Scanner LED lit up when cat is in proximity. |
| ![LED Off](path/to/led_off.jpg) | Scanner LED off when cat is out of proximity. |

*(Replace `path/to/` with your actual image paths.)*

---

## Limitations & Future Work

- **Range:** Current detection range is limited to a few meters (single room).
- **Power:** Battery wiring for beacon is challenging; portable charger is a workaround.
- **Delay:** There is a short delay (a few seconds) in detection and notification.
- **Interference:** Other Bluetooth devices can affect detection reliability.

**Future Improvements:**
- Integrate push notifications to mobile devices.
- Add temperature sensor for extra pet safety.
- Use beacon as a FOB key for automated cat doors.
- Improve battery integration and waterproofing.
- Optimize code for faster, more reliable detection.

---

## Reflections

- Tutorials on Arduino and Feather board were essential for rapid prototyping.
- Serial monitor was invaluable for debugging.
- Inspiration came from self-tracking and ubiquitous computing concepts.
- The project enhanced our skills in physical computing, prototyping, and teamwork.

---

## Inspiration & Related Work

- **Microchip GPS trackers:** Used by veterinarians for pet location.
- **Apple AirTag:** Bluetooth-based tracker for pets.
- **Smart Cat Doors:** Automated doors that detect pet presence.
- **Academic Inspiration:**  
  - Neff’s “Self-Tracking” - using technology for real-time monitoring.
  - Weiser’s “Ubiquitous Computing” - integrating computers seamlessly into daily life.

---

## Acknowledgments

- Dr. Sutherland for code samples and guidance.
- Adafruit and Arduino communities for hardware support.
- Class tutorials for foundational skills.

---
