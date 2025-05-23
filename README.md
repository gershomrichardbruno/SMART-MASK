# 🩺 Smart Mask - IoT-Based Health Monitoring System

This project is a wearable **Smart Mask** powered by an **ESP32 microcontroller** that continuously monitors vital signs such as **SpO2**, **heart rate**, **body temperature**, and **respiration rate**. It transmits real-time **SpO2** and **respiration rate** data to the **ThingSpeak IoT cloud platform** for online monitoring, while printing detailed waveform data to the Serial Monitor.

## 📌 Features

- 🔴 SpO2 and heart rate detection using MAX30102
- 🌡️ Body temperature sensing using DS18B20
- 🌬️ Respiration rate estimation from thermal data
- ☁️ IoT data upload to ThingSpeak (SpO2 & Respiration Rate)
- 🖥️ Serial Monitor display of all vitals and respiration waveform

---

## 🔧 Hardware Components

| Component         | Quantity | Description                       |
|------------------|----------|-----------------------------------|
| ESP32 Dev Board   | 1        | Microcontroller with WiFi         |
| MAX30102 Sensor   | 1        | SpO2 and heart rate sensor        |
| DS18B20 Sensor    | 1        | Digital temperature sensor        |
| Resistor 4.7kΩ    | 1        | For DS18B20 pull-up               |
| Jumper Wires      | -        | For wiring                        |
| Breadboard        | 1        | For prototyping                   |

---

## 🔌 Wiring Diagram

**MAX30102**
- VIN → 3.3V
- GND → GND
- SDA → GPIO 21
- SCL → GPIO 22

**DS18B20**
- VCC → 3.3V
- GND → GND
- DATA → GPIO 4 (with 4.7kΩ pull-up to 3.3V)

---

## 🧠 Software & Libraries

### ✅ Required Libraries (install via Arduino IDE Library Manager):

- `WiFi.h`
- `ThingSpeak.h`
- `OneWire.h`
- `DallasTemperature.h`
- `MAX30105.h` (from SparkFun)
- `spo2_algorithm.h` (manual add if needed)

---

## 💻 How It Works

1. Sensors read body temperature and SpO2/HR.
2. Respiration rate is estimated from temperature waveform using zero-crossing logic.
3. ESP32 connects to WiFi and pushes **SpO2** and **Respiration Rate** to **ThingSpeak** every 30 seconds.
4. Serial Monitor displays:
   - All real-time values
   - Raw waveform data for plotting

---

## 🌐 ThingSpeak Setup

1. Create a free account at [https://thingspeak.com](https://thingspeak.com)
2. Create a new channel:
   - Field 1: SpO2
   - Field 2: Respiration Rate
3. Get your **Channel ID** and **Write API Key**
4. Paste them into the Arduino code.

---

## 📂 File Structure



