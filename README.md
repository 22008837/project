# Smart Wastewater pH Monitoring and Alert System

**Small Description:**
The Smart Wastewater pH Monitoring and Alert System is designed to continuously monitor the pH level of wastewater in real time and provide instant alerts when abnormal conditions are detected, ensuring environmental safety and efficient water management.

---

## About

The Smart Wastewater pH Monitoring and Alert System is an IoT-based project developed to monitor the acidity and alkalinity of wastewater using real-time sensors and automated alert mechanisms. Wastewater discharged from industries and residential areas can significantly impact the environment if pH levels exceed permissible limits.

Traditional wastewater monitoring methods rely on manual sampling and laboratory testing, which are time-consuming and prone to delays. This project overcomes these limitations by integrating pH sensors, a microcontroller, and cloud-based monitoring to provide continuous observation and instant alerts.

The system detects abnormal pH values and notifies authorities through alerts, enabling timely corrective action. This solution improves efficiency, reduces environmental risks, and supports sustainable wastewater management practices.

---

## Features

- Real-time monitoring of wastewater pH levels
- Automated alert system for abnormal pH values
- IoT-based data acquisition and cloud integration
- High accuracy and reliability of sensor readings
- Low power consumption and cost-effective design
- Scalable architecture for large-scale deployment
- User-friendly dashboard for visualization of pH data

---

## Requirements

- **Operating System:** Windows 10 / Ubuntu (64-bit)
- **Hardware Components:**
  - pH Sensor (Analog)
  - Microcontroller: ESP32 Dev Board
  - Breadboard and jumper wires
  - Power Supply / USB
- **Programming Language:** Embedded C (Arduino IDE)
- **IoT Platform:** Blynk
- **Software Tools:** Arduino IDE 2.3.7
- **Communication:** Wi-Fi (ESP32 built-in)

---
## Project Documentation

Detailed project documentation is available below:

-  [Components List](Hardware/Components.md)
-  [Hardware Connections](Hardware/Hardware_connection.md)
-  [System Architecture](Architecture/System_architecture.md)
---

## Input

The following images show the **hardware components and physical setup** used as input to the system.

### ESP32 Dev Board Pinout

<img width="727" height="508" alt="input_esp32_pinout jpeg" src="https://github.com/user-attachments/assets/5865a279-d284-4407-9524-de28128622db" />

> The ESP32 Dev Module used in this project. The pH sensor analog output is connected to **GPIO35** (ADC input pin).

---

### Hardware Setup — pH Sensor in Water

<img width="960" height="1280" alt="input_hardware_setup_2 jpeg" src="https://github.com/user-attachments/assets/537ef93b-427c-42f7-8a21-32ee53e4cb0b" />
<img width="960" height="1280" alt="input_hardware_setup_1 jpeg" src="https://github.com/user-attachments/assets/ebc88c7f-b676-49e1-b068-6121d67be0f8" />

> The pH sensor probe is submerged in the wastewater sample and normal water (shown in the blue bowl). The ESP32 (red board, left) reads the analog voltage from the pH sensor module (green board, right) and processes it.

---

### Arduino IDE — Code & Configuration

![Arduino Code - Blynk Credentials](img/input_arduino_code_blynk.jpeg)

> The sketch configured with `BLYNK_TEMPLATE_ID`, `BLYNK_TEMPLATE_NAME`, `BLYNK_AUTH_TOKEN`, Wi-Fi SSID/password, and pH sensor on **PIN 35**.

![Arduino Code - pH Calculation Logic](img/input_arduino_code_logic.jpeg)

> The `sendData()` function reads the ADC value, converts it to voltage, computes the pH using the calibration formula:
> `pH = 7 + ((2.5 - voltage) / 0.18)`
> and sends the result to Blynk virtual pins V0 and V1.

---

## Output

The following images show the **system outputs** — serial monitor readings and Blynk app alerts.

### Serial Monitor — pH Readings

<img width="1600" height="900" alt="output_serial_acidic jpeg" src="https://github.com/user-attachments/assets/dcd8f5b7-9188-4071-a198-32c190654e42" />

> Serial Monitor showing readings when the sensor is in acidic water:
> `ADC: 4095 | Voltage: 3.30 | pH: 2.56 

<img width="1600" height="900" alt="output_serial_alkaline jpeg" src="https://github.com/user-attachments/assets/fd7fe645-5998-4544-bb45-56bfc3ade8dd" />

> Serial Monitor showing readings when the probe is in alkaline water:
> `ADC: ~2550 | Voltage: ~2.06 | pH: ~9.43 `

<img width="1600" height="900" alt="output_serial_neutral jpeg" src="https://github.com/user-attachments/assets/d3eda8bd-5817-429d-bcf2-be995f7b2973" />

> Serial Monitor showing pH transitioning through neutral range as conditions change.

---

### Blynk App — pH Alert Notification

<img width="625" height="1280" alt="output_blynk_alert jpeg" src="https://github.com/user-attachments/assets/c45a57e4-cc2f-4896-b189-cefc61d62803" />


>
> The Blynk mobile app displaying a push notification alert:
> **"⚠️ ALERT: pH level is unsafe!"**
> This is triggered automatically when the pH reading goes outside the safe range (below 6.5 or above 8.5).

---

## Results and Impact

The Smart Wastewater pH Monitoring and Alert System significantly improves the efficiency of wastewater quality management by providing continuous and automated monitoring. It reduces dependency on manual testing and enables faster detection of hazardous conditions.

This system helps prevent environmental pollution, protects aquatic life, and ensures compliance with wastewater discharge standards. The project demonstrates the effective use of IoT and sensor technologies in environmental monitoring and lays a strong foundation for smart city and sustainable development applications.

---

## Articles Published / References

1. S. R. Patil, A. A. Kulkarni, "IoT-Based Water Quality Monitoring System," *International Journal of Engineering Research*, vol. 9, no. 4, 2023.
2. WHO, "Guidelines for Wastewater Quality and Environmental Safety," World Health Organization, 2022.
3. M. R. Kumar, "Smart Environmental Monitoring Using IoT," *IEEE Conference on Smart Systems*, 2023.
