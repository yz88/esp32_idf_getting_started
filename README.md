# ESP32 IDF - Getting started

[ESP-IDF (Espressif IoT Development Framework)](https://docs.espressif.com/projects/esp-idf/en/stable/index.html#) is the official development framework for the ESP32 chip powered by [Espressif Systems](https://www.espressif.com/en).

- [ESP-IDF programming guide](https://docs.espressif.com/projects/esp-idf/en/stable/index.html#)
- [esp-idf git repository](https://github.com/espressif/esp-idf)
- [esp-idf-template git repository](https://github.com/espressif/esp-idf-template)
- [heise Make Magazin 3/2019 page 94 | ESP32 - Vollzugriff](https://www.heise.de/select/make/2019/3/1561289652311894)

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

## Update ESP-IDF

```bash
$ git show
commit 143d26aa49df524e10fb8e41a71d12e731b9b71d (HEAD, tag: v3.3.1)
Merge: 0407ab426 e1eabe6f6
Author: Ivan Grokhotkov <ivan@espressif.com>
Date:   Wed Dec 11 14:23:07 2019 +0800

    Merge branch 'bugfix/doc_package_versions_v3.3' into 'release/v3.3'

    doc: Limit sphinxcontrib versions to <2.0.0 as we use Sphinx 1.8.5 (v3.3)

    See merge request espressif/esp-idf!6975
```

```bash
$ git fetch
remote: Enumerating objects: 7536, done.
remote: Counting objects: 100% (7536/7536), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 18319 (delta 7532), reused 7536 (delta 7532), pack-reused 10783
Empfange Objekte: 100% (18319/18319), 8.61 MiB | 9.11 MiB/s, Fertig.
Löse Unterschiede auf: 100% (13806/13806), abgeschlossen mit 2689 lokalen Objekten.
Von https://github.com/espressif/esp-idf
   dd8db6621..2e14149bf  master       -> origin/master
   30fc65fcf..8f958c801  release/v3.1 -> origin/release/v3.1
   2a6a2bf39..58197e934  release/v3.2 -> origin/release/v3.2
   e28c5127c..1ba3bf297  release/v3.3 -> origin/release/v3.3
   aa51829ec..a3f3c7bdc  release/v4.0 -> origin/release/v4.0
 * [neuer Branch]        release/v4.1 -> origin/release/v4.1
 * [neuer Branch]        release/v4.2 -> origin/release/v4.2
 * [neues Tag]           v3.3.2       -> v3.3.2
 * [neues Tag]           v4.0         -> v4.0
 * [neues Tag]           v4.0-rc      -> v4.0-rc
 * [neues Tag]           v4.1-beta1   -> v4.1-beta1
 * [neues Tag]           v4.2-dev     -> v4.2-dev
Fetching submodule components/bt/lib
Von https://github.com/espressif/esp32-bt-lib
   0a707c8..e89bf97  master       -> origin/master
   2c9e7ec..6c0ad5a  release/v3.1 -> origin/release/v3.1
   d60b092..21d16b1  release/v3.2 -> origin/release/v3.2
   bd605c2..7a971f3  release/v3.3 -> origin/release/v3.3
 * [neuer Branch]    release/v4.0 -> origin/release/v4.0
Fetching submodule components/esp32/lib
Von https://github.com/espressif/esp32-wifi-lib
   8944eec..1b4c0c4  master       -> origin/master
   922e48e..4d9849b  release/v3.1 -> origin/release/v3.1
   a94d8b9..3b37918  release/v3.2 -> origin/release/v3.2
   b287033..19aa91f  release/v3.3 -> origin/release/v3.3
   c3fa441..674f73c  release/v4.0 -> origin/release/v4.0
 * [neuer Branch]    release/v4.1 -> origin/release/v4.1
Fetching submodule components/esptool_py/esptool
Von https://github.com/espressif/esptool
 * [neuer Branch]    feature/standalone_builds -> origin/feature/standalone_builds
   e28e839..1afa719  master     -> origin/master
 * [neuer Branch]    release/v2 -> origin/release/v2
Fetching submodule components/lwip/lwip
Von https://github.com/espressif/esp-lwip
   6a587ae2..da2740fa  2.0.3-esp  -> origin/2.0.3-esp
   b4eaf11f..5c181728  2.1.2-esp  -> origin/2.1.2-esp
Fetching submodule components/mbedtls/mbedtls
Von https://github.com/espressif/mbedtls
 * [neuer Branch]        mbedtls-2.16.4-idf -> origin/mbedtls-2.16.4-idf
 * [neuer Branch]        mbedtls-2.16.5-idf -> origin/mbedtls-2.16.5-idf
Fetching submodule components/mqtt/esp-mqtt
Von https://github.com/espressif/esp-mqtt
   86fc8b7..0c3d306  master     -> origin/master
Fetching submodule components/nimble/nimble
Von https://github.com/espressif/esp-nimble
   b2ae70c3..591721b7  nimble-1.1.0-idf      -> origin/nimble-1.1.0-idf
   8326807c..5364a96f  nimble-1.1.0-idf-v3.3 -> origin/nimble-1.1.0-idf-v3.3
   e2619190..14c6734c  nimble-1.1.0-idf-v3.3-afr -> origin/nimble-1.1.0-idf-v3.3-afr
   4a4be394..0a1604a5  nimble-1.2.0-idf      -> origin/nimble-1.2.0-idf
```

```bash
$ git checkout v4.0
warning: unable to rmdir 'components/aws_iot/aws-iot-device-sdk-embedded-C': Directory not empty
warning: unable to rmdir 'components/bt/lib': Directory not empty
warning: unable to rmdir 'components/esp32/lib': Directory not empty
warning: unable to rmdir 'components/micro-ecc/micro-ecc': Directory not empty
warning: unable to rmdir 'components/nimble/nimble': Directory not empty
Checke Dateien aus: 100% (4618/4618), Fertig.
M       components/coap/libcoap
M       components/lwip/lwip
M       components/mqtt/esp-mqtt
Vorherige Position von HEAD war 143d26aa4 Merge branch 'bugfix/doc_package_versions_v3.3' into 'release/v3.3'
HEAD ist jetzt bei 463a9d8b7 Merge branch 'bugfix/ci_deploy_tags_v4.0' into 'release/v4.0'
```

```bash
$ git show
commit 463a9d8b7f9af8205222b80707f9bdbba7c530e1 (HEAD, tag: v4.0-rc, tag: v4.0)
Merge: aa51829ec ef34e6f6f
Author: Ivan Grokhotkov <ivan@espressif.com>
Date:   Sat Jan 11 14:08:55 2020 +0800

    Merge branch 'bugfix/ci_deploy_tags_v4.0' into 'release/v4.0'

    ci: fix tags for internal deploy jobs (backport v4.0)

    See merge request espressif/esp-idf!7295
```