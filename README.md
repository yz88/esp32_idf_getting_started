# ESP32 IDF - Getting started

[ESP-IDF (Espressif IoT Development Framework)](https://docs.espressif.com/projects/esp-idf/en/stable/index.html#) is the official development framework for the ESP32 chip powered by [Espressif Systems](https://www.espressif.com/en).

- [ESP-IDF programming guide](https://docs.espressif.com/projects/esp-idf/en/stable/index.html#)
- [esp-idf git repository](https://github.com/espressif/esp-idf)
- [heise developer - ESP32 to go](http://www.heise.de/-4452689)

**Q: Why using ESP-IDF?**

A: The benefit of ESP-IDF (over Arduino APIs) is that the ESP-IDF is native to the ESP32 (by definition). It is the API that will give you the highest fidelity against the ESP32 device itself. There are capabilities available in ESP-IDF that aren't (yet?) present in mapped Arduino APIs.

The Arduino IDE provides easy access to the ESP32. But if you want to take full control, you can use the developer framework ESP-IDF from Espressif. The ESP-IDF is the basis for the arduino-esp32 project, which enables the development of ESP32 software with the Arduino-IDE.

## Standard setp of toolchain for Windows

Follow the instructions on <https://docs.espressif.com/projects/esp-idf/en/stable/get-started/windows-setup.html>

1. download Windows all-in-one toolchain
2. create directory as you want, e.g. `C:\Users\yourName\Documents\esp32-dev-env\`
3. unzip Windows toolchain to that directory
4. Open a MSYS2 MINGW32 terminal window by running `C:\Users\yourName\Documents\esp32-dev-env\msys32\mingw32.exe`
5. `mkdir -p ~/esp`
6. `cd ~/esp`
7. `git clone -b v3.3.1 --recursive https://github.com/espressif/esp-idf.git`
8. ESP-IDF will be downloaded into `~/esp/esp-idf`
9. `cd esp-idf`
10. `git submodule update --init --recursive`
11. setup path in develpoment environment
    1. Create a new script file in `C:\Users\yourName\Documents\esp32-dev-env\msys32\etc\profile.d` directory. Name it `export_idf_path.sh`.
    2. Identify the path to ESP-IDF directory. It is specific to your system configuration and may look something like `C:\Users\yourName\Documents\esp32-dev-env\msys32\home\user-name\esp\esp-idf`
    3. Add the export command to the script file: `export IDF_PATH="C:/Users/yourName/Documents/esp32-dev-env/msys32/home/user-name/esp/esp-idf"`
    4. Save the script file.
    5. Close MSYS2 window and open it again. Check if `IDF_PATH` is set, by typing: `printenv IDF_PATH`
12. Connect ESP32 via microUSB to your Windows PC and check the allocated COM port via Windows device manager. Use Windows like COM Port in the configuration of each project.
13. [Start the first project](https://docs.espressif.com/projects/esp-idf/en/stable/get-started/index.html#start-a-project)