# Electrochemical-Sensor-Data-Acquisition
An Arduino-based data acquisition system for electrochemical three-electrode sensors. It uses a potentiostat circuit and op-amps for signal amplification, logs real-time data via Arduino ADC, and supports analysis in MATLAB, Python, or Excel. Ideal for biosensing, monitoring, and chemical analysis.
# Electrochemical-Sensor-Data-Acquisition

An Arduino-based data acquisition system designed for interfacing with a three-electrode electrochemical sensor. The system collects analog sensor signals, digitizes the data, and transmits it to a PC for real-time monitoring or further analysis.

---

##  Project Overview

This project aims to develop a low-cost, flexible, and reliable data acquisition circuit for electrochemical sensing experiments. The circuit uses an Arduino board to sample the analog output of a three-electrode sensor setup and logs the readings via serial communication.

---

## ⚙️ Components Used

| Component                     | Quantity |
|--------------------------------|----------|
| Arduino UNO / Nano / Mega      | 1        |
| Electrochemical Sensor (3-electrode) | 1        |
| Op-Amp (e.g., TL072)           | 1-2      |
| Resistors (various values)     | As needed |
| Capacitors (various values)    | As needed |
| Breadboard / PCB               | 1        |
| Jumper Wires                   | As needed |
| USB Cable                      | 1        |

---

## 🔌 Circuit Overview

- The three-electrode sensor outputs are conditioned using an op-amp circuit.
- The conditioned analog signal is fed into the Arduino’s ADC input (typically `A0`).
- Arduino converts this signal to digital form and sends the data via serial to a computer.
- The collected data can be logged or plotted in real-time using Serial Plotter or other tools.

---

## 💻 Firmware

The Arduino sketch reads analog values from the sensor and transmits them via serial:

```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(A0);
  Serial.println(sensorValue);
  delay(100);  // Adjust sampling rate as needed
}
