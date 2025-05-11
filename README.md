# 🚧 Smart Ultrasonic Barrier Gate System

This Arduino project implements a **smart gate system** that automatically opens and closes a barrier based on proximity sensing using an ultrasonic sensor. It simulates a basic vehicle detection and access control mechanism using a servo motor, LEDs, and a buzzer for visual and audio feedback.

## 🔧 Hardware Used

- Arduino UNO/Nano/compatible board
- HC-SR04 Ultrasonic Sensor
- SG90 Servo Motor
- Red LED + Resistor
- Blue LED + Resistor
- Buzzer
- Jumper wires
- Breadboard

---

## 📌 Features

- 🚗 **Object Detection**: Uses ultrasonic sensor to detect objects within 10 cm.
- 🚦 **Visual Indicators**: 
  - Red LED when gate is closed.
  - Blue LED when gate is open.
- 🎵 **Buzzer Beep**: Buzzer beeps when gate is open.
- 🔁 **Auto-close Logic**: Gate closes after 5 seconds if no object is detected.
- ⚙️ **Servo Control**: Opens and closes the gate based on detection.

---

## 📐 Pin Configuration

| Component           | Arduino Pin |
|---------------------|-------------|
| Ultrasonic Trigger  | 2           |
| Ultrasonic Echo     | 3           |
| Red LED Anode       | 4           |
| Red LED Cathode     | 8 (GND)     |
| Blue LED Cathode    | 7 (GND)     |
| Blue LED            | 5           |
| Servo Motor         | 6           |
| Buzzer              | 12          |

---

## 📄 How It Works

1. When an object is detected within `10 cm`, the gate opens:
    - Servo moves to `90°`
    - Blue LED turns on
    - Buzzer starts beeping every 0.5 seconds

2. Once the object leaves and after `5 seconds` of no detection:
    - Servo returns to `0°`
    - Red LED turns on
    - Buzzer stops

---

## 🧠 Code Logic Highlights

- `getDistance()` → Measures distance using ultrasonic sensor.
- `loop()` → Monitors distance, updates servo, LEDs, and buzzer.
- Uses `millis()` for non-blocking delay and timing control.

---

## 📂 File Structure

```plaintext
smart-barrier-gate/
│
├── SmartBarrierGate.ino       # Main Arduino code
├── README.md                  # Project documentation
```

## 🛠 Setup Instructions
   - Clone this repo or copy the code to your Arduino IDE.
   - Connect the components as per the pin configuration.
   - Upload the code to your Arduino board.
   - Power on and test the system.

