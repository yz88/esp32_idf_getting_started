# ESP32 IDF - Getting started

[ESP-IDF (Espressif IoT Development Framework)](https://docs.espressif.com/projects/esp-idf/en/stable/index.html#) is the official development framework for the ESP32 chip powered by [Espressif Systems](https://www.espressif.com/en).

- [ESP-IDF programming guide](https://docs.espressif.com/projects/esp-idf/en/stable/index.html#)
- [esp-idf git repository](https://github.com/espressif/esp-idf)

**Q: Why using ESP-IDF?**

A: The benefit of ESP-IDF (over Arduino APIs) is that the ESP-IDF is native to the ESP32 (by definition). It is the API that will give you the highest fidelity against the ESP32 device itself. There are capabilities available in ESP-IDF that aren't (yet?) present in mapped Arduino APIs.

The Arduino IDE provides easy access to the ESP32. But if you want to take full control, you can use the developer framework ESP-IDF from Espressif. The ESP-IDF is the basis for the arduino-esp32 project, which enables the development of ESP32 software with the Arduino-IDE.
