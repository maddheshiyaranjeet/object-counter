# 🔌 Object Counter Using LED Matrix Display

## 📖 Project Description

This project demonstrates an **electronic object counting system** that uses a sensor and a microcontroller to detect objects and display the count on an LED matrix display. It is a simple yet practical embedded system project suitable for beginners and intermediate electronics enthusiasts.

The system is widely applicable in automation tasks such as counting items on a conveyor belt or tracking the number of people entering a space.

---

## 🎯 Objectives

* To design a real-time object counting system
* To interface a sensor with a microcontroller
* To display numerical data using an LED matrix
* To understand basic embedded system design

---

## 🧠 Working Principle

The system operates based on object detection:

* A sensor (IR or ultrasonic) detects an object passing in front of it
* The microcontroller processes the signal
* Each detection increments a counter
* The updated count is displayed on the LED matrix
* A delay or debounce mechanism prevents false multiple counts

---

## 🧰 Hardware Components

* Microcontroller (Arduino Uno / ESP32 / similar)
* IR Sensor Module (or Ultrasonic Sensor)
* LED Matrix Display (MAX7219-based recommended)
* Push Button (for reset, optional)
* Resistors
* Jumper wires
* Breadboard / PCB
* Power Supply (5V)

---

## 🔗 System Block Diagram

```
[ Object ] → [ Sensor ] → [ Microcontroller ] → [ LED Matrix Display ]
                                  ↓
                             [ Reset Button ]
```

---

## 🔌 Circuit Connections (Overview)

* Sensor OUT → Digital Pin (e.g., D2)
* LED Matrix:

  * DIN → D11
  * CLK → D13
  * CS → D10
* VCC → 5V
* GND → GND

*(Exact connections may vary depending on hardware used)*

---

## 💻 Software Requirements

* Arduino IDE
* Libraries:

  * `LedControl` or `MD_MAX72XX`
  * `SPI` (for matrix communication)

---

## 🧑‍💻 Implementation Steps

1. Assemble the circuit as per the connections.
2. Install required libraries in Arduino IDE.
3. Write or upload the object counter code.
4. Power the circuit.
5. Place objects in front of the sensor to test counting.

---

## 🧾 Example Code

```cpp
#include <LedControl.h>

int sensorPin = 2;
int count = 0;

void setup() {
  pinMode(sensorPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  if (digitalRead(sensorPin) == LOW) {
    count++;
    Serial.println(count);
    delay(500); // debounce delay
  }
}
```

---

## 📊 Expected Output

* The LED matrix displays the number of detected objects
* Count increases with each object detected
* Reset button (if included) clears the count

---

## 🚀 Applications

* Industrial object counting
* Visitor counting systems
* Smart inventory systems
* Automation and robotics projects

---

## ⚠️ Limitations

* May miscount if objects move too fast
* Sensitive to environmental interference (light, distance)
* Requires calibration for accuracy

---

## 🔧 Future Enhancements

* Add IoT connectivity for remote monitoring
* Store data in EEPROM or cloud
* Use multiple sensors for bidirectional counting
* Improve UI with larger displays



