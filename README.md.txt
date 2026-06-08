# 🚗 Alcohol Detection with Engine Locking System

A safety-focused embedded system that detects alcohol levels using an MQ-3 gas sensor and automatically locks the vehicle engine when the reading exceeds a safe threshold — preventing drunk driving incidents.

---

## 📌 Overview

This project uses an Arduino microcontroller and an MQ-3 alcohol sensor to continuously monitor blood-alcohol equivalent levels. When the detected level crosses a defined threshold, a relay-controlled motor is disabled — simulating an engine lock mechanism. Real-time feedback is provided via the Arduino serial monitor.

---

## 🛠️ Components Used

| Component | Purpose |
|---|---|
| Arduino Uno | Main microcontroller |
| MQ-3 Gas Sensor | Detects alcohol/ethanol levels |
| Relay Module | Controls engine (motor) power |
| DC Motor | Simulates vehicle engine |
| LED Indicators | Visual alert for driver |
| Jumper Wires & Breadboard | Circuit connections |

---

## ⚙️ How It Works

1. The **MQ-3 sensor** continuously reads alcohol concentration in the air
2. The Arduino reads the analog output and compares it to a **calibrated threshold**
3. If the reading is **below threshold** → engine runs normally ✅
4. If the reading **exceeds threshold** → relay cuts power to motor (engine locked) 🔒
5. A **serial monitor alert** is displayed in real-time for logging and debugging
6. **Debounce logic** prevents false positives from brief spikes in sensor readings

---

## 📊 Features

- ✅ Real-time alcohol level monitoring
- ✅ Automatic engine lock on detection
- ✅ Threshold calibration to reduce false positives by ~30%
- ✅ Serial monitor feedback for system state logging
- ✅ Debounce logic for signal stability
- ✅ Tested on virtual simulation (Wokwi/Tinkercad) before physical deployment

---

## 🔌 Circuit Diagram

> ![Circuit Diagram](circuit_diagram.png)`

---

## 💻 Code

The main code is in `alcohol_detection.ino`

```cpp
// Key logic snippet
int sensorValue = analogRead(A0);
if (sensorValue > THRESHOLD) {
    digitalWrite(RELAY_PIN, LOW);  // Lock engine
    Serial.println("ALERT: High alcohol detected! Engine locked.");
} else {
    digitalWrite(RELAY_PIN, HIGH); // Engine runs
    Serial.println("Status: Normal. Engine running.");
}
```

---

## 🚀 How to Run

1. Connect components as per the circuit diagram
2. Open **Arduino IDE**
3. Upload `alcohol_detection.ino` to your Arduino Uno
4. Open **Serial Monitor** (baud rate: 9600)
5. Blow near the MQ-3 sensor to test detection
6. Observe relay switching and serial monitor output

---

## 📷 Demo

> https://drive.google.com/file/d/1o6xRzPoTGX63g5ihlTh3CuXUsZ6p85CW/view?usp=drivesdk

---

## 👩‍💻 Author

**Shaik Madiha**
ECE Graduate | Embedded Systems | IoT | Arduino | C++
- 📧 madihashaik82@email.com
- 🔗 [LinkedIn]https://www.linkedin.com/in/shaik-madiha-23996927b?utm_source=share_via&utm_content=profile&utm_medium=member_android
- 💻 [GitHub](https://github.com/shaik-madiha)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
