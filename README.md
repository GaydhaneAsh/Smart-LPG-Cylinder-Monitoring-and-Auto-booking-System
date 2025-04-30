# 🔥 Smart LPG Cylinder Monitoring and Auto Booking System

An IoT-based solution to monitor LPG cylinder levels in real-time using a load cell, with automatic SMS and call alerts when the gas level is low. It includes buzzer-based local alerting and reset functionality after a refill is detected.

---

## 🎯 Objective

The objective of this project is to **design and develop an automated LPG booking system** that can efficiently monitor the weight of a gas cylinder using **load cells** and an **HX711 amplifier**. The system aims to detect when the gas level falls below a predefined threshold and automatically **initiate booking by making call attempts** through the **SIM800L GSM module**. If repeated call attempts fail, it is intended to **send an SMS alert** to ensure that booking is completed without manual intervention.

Additionally, the system seeks to:
- Display real-time gas status on a **1602 LCD module** for user awareness,
- Ensure reliable communication through a **rechargeable battery-powered GSM unit**, and
- Promote **safer, more convenient, and energy-efficient** management of LPG for both **household and commercial users**.

---

## 🚀 Features

- 📉 Real-time monitoring of LPG cylinder weight using a load cell and HX711 amplifier
- 📟 LCD display for current weight and system status
- 🔔 Buzzer alert when LPG level falls below a safe threshold (150g)
- 📲 Sends SMS and initiates a call via SIM800L GSM module
- 🔄 Auto-reset after refill detection (weight > 300g)
- 🔘 Manual button to silence buzzer and acknowledge alerts
- ✅ Debounce logic for stable button operation

---

## 🧰 Components Used

| Component         | Description                                |
|------------------|--------------------------------------------|
| Arduino UNO R3    | Microcontroller for processing and control |
| HX711 Module      | 24-bit ADC for load cell data              |
| Load Cell         | Measures weight of the LPG cylinder        |
| SIM800L Module    | GSM module for SMS and call functionality  |
| Buzzer            | Audio alert for low gas level              |
| Push Button       | User acknowledgment/reset input            |
| LCD with I2C      | Display weight and status messages         |
| Power Supply      | 5V/9V source (regulated for GSM module)    |

---

## ⚙️ System Workflow

1. **Startup**: System initializes and starts weight monitoring.
2. **Normal Monitoring**: Displays current LPG weight and status on the LCD.
3. **Low Weight Detection**: 
   - If weight < 150g:
     - Buzzer turns ON
     - SMS is sent and a call is triggered to the registered number
4. **Acknowledgment**:
   - User presses the button to silence the buzzer.
5. **Refill Detection**:
   - If weight > 300g:
     - System auto-resets and enters normal monitoring mode.

---

## 🖥️ Circuit Connections

| Component       | Arduino Pin |
|----------------|-------------|
| HX711 DOUT     | 4           |
| HX711 SCK      | 5           |
| Buzzer +       | 7           |
| Button         | 8           |
| LCD (I2C SDA)  | A4          |
| LCD (I2C SCL)  | A5          |
| SIM800L TX     | D10 (via SoftwareSerial) |
| SIM800L RX     | D11 (via SoftwareSerial) |

> 📌 **Note**: Use a separate power supply or voltage regulator for SIM800L to avoid reset issues.

---

## 🧪 Thresholds

- **Alert Trigger**: < 150g  
- **Auto Reset**: > 300g  

Adjust these in the Arduino code if needed based on your cylinder type.

---

## 📸 Project Preview

>![image](https://github.com/user-attachments/assets/9738f401-2fd0-410f-ae7b-99775ee25c9a)


---
