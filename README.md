# 16 channel servo driver with arduino nano

A simple Arduino-based robotic motion system that controls **three servo motors in sequence**.

The project uses an **Arduino Nano** and a **PCA9685 16-channel servo driver** to control the servos. 

---

## ✨ Features

* 🎛️ Touch-controlled operation
* 🤖 Controls 3 servo motors
* 🔄 Sequential servo movement
* ⚡ PCA9685 servo driver for reliable PWM control
* 🧠 Arduino Nano based
* 🔧 Easy to modify and expand

---

## 🧰 Components

| Component                       |    Quantity |
| ------------------------------- | ----------: |
| Arduino Nano                    |           1 |
| PCA9685 16-Channel Servo Driver |           1 |
| Servo Motor                     |           3 |
| External 5–6V Power Supply      |           1 |
| Jumper Wires                    | As required |

---

## 🔌 Wiring

### Arduino Nano → PCA9685

| Arduino Nano | PCA9685 |
| ------------ | ------- |
| 5V           | VCC     |
| GND          | GND     |
| A4           | SDA     |
| A5           | SCL     |
| GND          | OE      |

### Servos → PCA9685

| Servo   | PCA9685 Channel |
| ------- | --------------- |
| Servo 1 | Channel 0       |
| Servo 2 | Channel 1       |
| Servo 3 | Channel 2       |

Each servo connects to the corresponding channel's:

```text
GND → Servo GND
V+  → Servo VCC
PWM → Servo Signal
```


> ⚠️ **Important:** Servos should preferably be powered using a separate 5–6V power supply. Do not draw the servo current directly from the Arduino Nano.

---

## ⚙️ How It Works

Servo 1
0° ──────────→ 180°
    │
    ▼
Servo 2
0° ──────────→ 180°
    │
    ▼
Servo 3
0° ──────────→ 180°
    │
    └──────────────→ Repeat
```

Only **one servo moves at a time**.


---

## 💻 Software

The project is programmed using the **Arduino IDE**.

### Required Library

Install the following library through:

**Arduino IDE → Library Manager**

```text
Adafruit PWM Servo Driver Library
```

The project uses the PCA9685 at its default I²C address:

```text
0x40
```

---

## 🚀 Getting Started

1. Connect the Arduino Nano to the PCA9685.
2. Connect the three servos to channels 0, 1, and 2.
3. Connect the touch sensor to pin D2.
4. Connect an appropriate external power supply for the servos.
5. Install the **Adafruit PWM Servo Driver Library**.
6. Open the `.ino` file in Arduino IDE.
7. Select the correct Arduino Nano board and COM port.
8. Upload the code.
9. Hold the touch sensor to start the motion.

---

## 📁 Project Structure

```text
3-servo-touch-controlled-mechanism/
│
├── README.md
│
├── src/
│   └── 3_servo_touch_control.ino
│
├── docs/
│   └── wiring.md
│
└── images/
    ├── project.jpg
    └── wiring.png
```

---

## 🛠️ Customization

The servo speed can be changed by modifying:

```cpp
delay(10);
```

A smaller value makes the servo move faster, while a larger value makes it move slower.

The servo range can also be changed:

```cpp
setServoAngle(channel, 0);
```

and

```cpp
setServoAngle(channel, 180);
```

For example, to limit the movement:

```cpp
setServoAngle(channel, 20);
```

to

```cpp
setServoAngle(channel, 160);
```

---

## 🔮 Future Improvements

Possible upgrades for this project include:

* 🎚️ Adjustable servo speed
* 🔘 Multiple touch sensors
* ↔️ Reverse movement
* 🕹️ Joystick control
* 📱 Bluetooth control
* 🖥️ OLED status display
* 🎛️ Individual servo control
* 💾 Saving custom motion sequences
* 🤖 Adding more servos

---



## ⚠️ Important Notes

* Make sure the servo power supply can provide enough current.
* Connect the external power supply **GND to Arduino GND**.
* Do not accidentally connect the external servo supply directly to the Nano's 5V pin.
* Servo limits vary between models. Avoid forcing a servo beyond its mechanical range.


---

## 📜 License

This project is open-source and available under the **MIT License**.

Feel free to modify, improve, and build upon it. 🚀

---

## ⭐ Support

If you found this project useful, consider giving the repository a ⭐ on GitHub!
