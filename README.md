# DAY-15
Smart Light Classifier



# SIG-05 AUTOMATRIX – Smart Light Classifier

## Objective

Develop a Smart Light Classifier using **ESP32, LDR sensor, OLED display, TinyML, WiFi, automatic LED control, and a web dashboard**.

The system measures the surrounding light level using an LDR sensor and uses an on-device TinyML model to classify the light condition as **Dark, Normal, or Bright**.

## System Workflow

```text
LDR Sensor
     ↓
ESP32
     ↓
TinyML Model
     ↓
Dark / Normal / Bright
     ↓
Automatic LED Control
     ↓
OLED Display
     ↓
WiFi
     ↓
Web Dashboard
     ↓
Log Sensor Readings
```

## Light Classification

| LDR Value   | Classification | LED Status |
| ----------- | -------------- | ---------- |
| 0 – 1200    | Dark           | ON         |
| 1201 – 2800 | Normal         | Controlled |
| 2801 – 4095 | Bright         | OFF        |

## Sample Output

```text
LDR: 500
Class: DARK
LED: ON

LDR: 2000
Class: NORMAL
LED: CONTROLLED

LDR: 3500
Class: BRIGHT
LED: OFF
```

## Technologies Used

* ESP32
* LDR Sensor
* OLED Display
* LED
* WiFi
* TensorFlow
* TensorFlow Lite
* TensorFlow Lite Micro
* TinyML
* Google Colab
* Web Dashboard

## Generated Files

* `SIG-05-Smart-Light-Classifier.ipynb` – Google Colab notebook used for training and TFLite conversion.
* `light_model.tflite` – Trained TinyML model.
* `light_model_data.h` – C/C++ header file containing the TinyML model for ESP32.
* `README.md` – Project documentation.

## TinyML Model

The model is trained using LDR sensor values and three classes:

* **Dark**
* **Normal**
* **Bright**

The trained TensorFlow model is converted into TensorFlow Lite format for deployment on the ESP32.

## Automatic LED Control

The ESP32 automatically controls the LED based on the TinyML prediction:

* **Dark → LED ON**
* **Normal → LED controlled**
* **Bright → LED OFF**

## OLED Display

The OLED displays the current sensor value and predicted light condition.

Example:

```text
SMART LIGHT

LDR: 3500
BRIGHT
LED: OFF
```

## Web Dashboard

The ESP32 uses WiFi to send sensor and classification results to a web dashboard.

The dashboard can display:

* LDR sensor value
* Light classification
* LED status
* WiFi connection status
* Logged sensor readings
* Time of each reading

## Result

The Smart Light Classifier integrates **sensor data, TinyML classification, automatic LED control, OLED display, WiFi communication, and web-based logging** into a single IoT system.

The system can identify the surrounding light condition and automatically control the LED based on the predicted class.

## Project Status

**TinyML model training and TFLite conversion completed.**

The trained model is prepared for ESP32 deployment and integration with the LDR sensor, OLED display, LED control, WiFi, and web dashboard.

