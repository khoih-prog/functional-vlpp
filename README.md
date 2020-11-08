## functional-vlpp Library

[![arduino-library-badge](https://www.ardu-badge.com/badge/Functional-Vlpp.svg?)](https://www.ardu-badge.com/Functional-Vlpp)
[![GitHub release](https://img.shields.io/github/release/khoih-prog/Functional-Vlpp.svg)](https://github.com/khoih-prog/Functional-Vlpp/releases)
[![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/khoih-prog/Functional-Vlpp/blob/master/LICENSE)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](#Contributing)
[![GitHub issues](https://img.shields.io/github/issues/khoih-prog/Functional-Vlpp.svg)](http://github.com/khoih-prog/Functional-Vlpp/issues)

---

### Version v1.0.1

1. Add support to and tested working **OK** in other architectures such as **Teensy, SAM, SAMD, STM32, eps8266, esp32** besides AVR.

### Initial Releases v1.0.0

1. Based on and modified from [**Marcus Rugger's functional-vlpp Library**](https://github.com/marcusrugger/functional-vlpp).

---

The original [vczh-libraries/Vlpp](https://github.com/vczh-libraries/Vlpp) provides common C++ construction, including string operation / generic container / linq, function templates to better support **C++ functional programming across platforms**. 

The `functional portion` of the project was then forked and modified to be used for Arduino by [Marcus Rugger functional-vlpp library](https://github.com/marcusrugger/functional-vlpp). 

This [**Functional-Vlpp library**](https://github.com/khoih-prog/Functional-Vlpp) is based on, modified to use and tested working **OK** in other architectures such as **Teensy, SAM, SAMD, STM32, eps8266, esp32**.

---
---

## Prerequisite

 1. [`Arduino IDE 1.8.13+` for Arduino](https://www.arduino.cc/en/Main/Software)
 2. [`Arduino AVR core 1.8.3+`](https://github.com/arduino/ArduinoCore-avr) for Arduino AVR boards. Use Arduino Board Manager to install.
 3. [`Arduino Core for STM32 v1.9.0+`](https://github.com/khoih-prog/Arduino_Core_STM32) for STM32 boards (Nucleo-144 NUCLEO_F767ZI, Nucleo-64 NUCLEO_L053R8, etc.)
 4. [`Teensy core 1.53+`](https://www.pjrc.com/teensy/td_download.html) for Teensy (4.1, 4.0, 3.6, 3.5, 3,2, 3.1, 3.0, LC) boards
 5. [`Arduino SAM DUE core 1.6.12+`](https://www.arduino.cc/en/Guide/ArduinoDue) for SAM DUE ARM Cortex-M3 boards
 6. [`Arduino SAMD core 1.8.9+`](https://www.arduino.cc/en/Guide/ArduinoM0) for SAMD ARM Cortex-M0+ boards  (Nano 33 IoT, etc.).
 7. [`Adafruit SAMD core 1.6.4+`](https://www.adafruit.com/)  for SAMD ARM Cortex-M0+ and M4 boards (Itsy-Bitsy M4, etc.)
 8. [`Seeeduino SAMD core 1.8.1+`](https://www.seeedstudio.com/) for SAMD21/SAMD51 boards (XIAO M0, Wio Terminal, etc.) 
 9. [`Adafruit nRF52 v0.21.0+`](www.adafruit.com) for nRF52 boards such as AdaFruit Feather nRF52840 Express, NINA_B302_ublox, NINA_B112_ublox, etc.
 

---

## Installation

### Use Arduino Library Manager

The best and easiest way is to use `Arduino Library Manager`. Search for `Functional-Vlpp`, then select / install the latest version.
You can also use this link [![arduino-library-badge](https://www.ardu-badge.com/badge/Functional-Vlpp.svg?)](https://www.ardu-badge.com/Functional-Vlpp) for more detailed instructions.

### Manual Install

1. Navigate to [Functional-Vlpp](https://github.com/khoih-prog/Functional-Vlpp) page.
2. Download the latest release `Functional-Vlpp-master.zip`.
3. Extract the zip file to `Functional-Vlpp-master` directory 
4. Copy whole 
  - `Functional-Vlpp-master` folder to Arduino libraries' directory such as `~/Arduino/libraries/`.

### VS Code & PlatformIO:

1. Install [VS Code](https://code.visualstudio.com/)
2. Install [PlatformIO](https://platformio.org/platformio-ide)
3. Install [**Functional-Vlpp** library](https://platformio.org/lib/show/7082/Functional-Vlpp) by using [Library Manager](https://platformio.org/lib/show/7082/Functional-Vlpp/installation). Search for **Functional-Vlpp** in [Platform.io Author's Libraries](https://platformio.org/lib/search?query=author:%22Khoi%20Hoang%22)
4. Use included [platformio.ini](platformio/platformio.ini) file from examples to ensure that all dependent libraries will installed automatically. Please visit documentation for the other options and examples at [Project Configuration File](https://docs.platformio.org/page/projectconf.html)

---

### Packages' Patches

 1. **To be able to compile, run and automatically detect and display BOARD_NAME on nRF52840/nRF52832 boards**, you have to copy the whole [nRF52 0.21.0](Packages_Patches/adafruit/hardware/nrf52/0.21.0) directory into Adafruit nRF52 directory (~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0). 

Supposing the Adafruit nRF52 version is 0.21.0. These files must be copied into the directory:
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/platform.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/boards.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B302_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B302_ublox/variant.cpp`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B112_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B112_ublox/variant.cpp`
- **`~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/cores/nRF5/Udp.h`**

Whenever a new version is installed, remember to copy these files into the new version directory. For example, new version is x.yy.z
These files must be copied into the directory:

- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/platform.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/boards.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B302_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B302_ublox/variant.cpp`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B112_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B112_ublox/variant.cpp`
- **`~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/cores/nRF5/Udp.h`**

 2. **To be able to compile and run on Teensy boards**, you have to copy the file [Teensy boards.txt](Packages_Patches/hardware/teensy/avr/boards.txt) into Teensy hardware directory (./arduino-1.8.12/hardware/teensy/avr/boards.txt). 

Supposing the Arduino version is 1.8.12. This file must be copied into the directory:

- `./arduino-1.8.12/hardware/teensy/avr/boards.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `./arduino-x.yy.zz/hardware/teensy/avr/boards.txt`

 3. **To be able to compile and run on SAM DUE boards**, you have to copy the whole [SAM DUE](Packages_Patches/arduino/hardware/sam/1.6.12) directory into Arduino sam directory (~/.arduino15/packages/arduino/hardware/sam/1.6.12). 

Supposing the Arduino SAM core version is 1.6.12. This file must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/sam/1.6.12/platform.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/sam/x.yy.zz/platform.txt`

 4. ***To be able to compile without error and automatically detect and display BOARD_NAME on Arduino SAMD (Nano-33-IoT, etc) boards***, you have to copy the whole [Arduino SAMD cores 1.8.9](Packages_Patches/arduino/hardware/samd/1.8.9) directory into Arduino SAMD directory (~/.arduino15/packages/arduino/hardware/samd/1.8.9).
 
Supposing the Arduino SAMD version is 1.8.9. These files must be copied into the directory:
- `~/.arduino15/packages/arduino/hardware/samd/1.8.9/platform.txt`
- ***`~/.arduino15/packages/arduino/hardware/samd/1.8.9/cores/arduino/Arduino.h`***

Whenever a new version is installed, remember to copy these files into the new version directory. For example, new version is x.yy.z

These files must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/samd/x.yy.z/platform.txt`
- ***`~/.arduino15/packages/arduino/hardware/samd/x.yy.z/cores/arduino/Arduino.h`***
 
 This is mandatory to fix the ***notorious Arduino SAMD compiler error***. See [Improve Arduino compatibility with the STL (min and max macro)](https://github.com/arduino/ArduinoCore-samd/pull/399)
 
```
 ...\arm-none-eabi\include\c++\7.2.1\bits\stl_algobase.h:243:56: error: macro "min" passed 3 arguments, but takes just 2
     min(const _Tp& __a, const _Tp& __b, _Compare __comp)
```

Whenever the above-mentioned compiler error issue is fixed with the new Arduino SAMD release, you don't need to copy the `Arduino.h` file anymore.

 5. ***To be able to automatically detect and display BOARD_NAME on Adafruit SAMD (Itsy-Bitsy M4, etc) boards***, you have to copy the file [Adafruit SAMD platform.txt](Packages_Patches/adafruit/hardware/samd/1.6.4) into Adafruit samd directory (~/.arduino15/packages/adafruit/hardware/samd/1.6.4). 

Supposing the Adafruit SAMD core version is 1.6.4. This file must be copied into the directory:

- `~/.arduino15/packages/adafruit/hardware/samd/1.6.4/platform.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `~/.arduino15/packages/adafruit/hardware/samd/x.yy.zz/platform.txt`

 6. ***To be able to automatically detect and display BOARD_NAME on Seeeduino SAMD (XIAO M0, Wio Terminal, etc) boards***, you have to copy the file [Seeeduino SAMD platform.txt](Packages_Patches/Seeeduino/hardware/samd/1.8.1) into Adafruit samd directory (~/.arduino15/packages/Seeeduino/hardware/samd/1.8.1). 

Supposing the Seeeduino SAMD core version is 1.8.1. This file must be copied into the directory:

- `~/.arduino15/packages/Seeeduino/hardware/samd/1.8.1/platform.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `~/.arduino15/packages/Seeeduino/hardware/samd/x.yy.zz/platform.txt`

7. **To use Serial1 on some STM32 boards without Serial1 definition (Nucleo-144 NUCLEO_F767ZI, Nucleo-64 NUCLEO_L053R8, etc.) boards**, you have to copy the files [STM32 variant.h](Packages_Patches/STM32/hardware/stm32/1.9.0) into STM32 stm32 directory (~/.arduino15/packages/STM32/hardware/stm32/1.9.0). You have to modify the files corresponding to your boards, this is just an illustration how to do.

Supposing the STM32 stm32 core version is 1.9.0. These files must be copied into the directory:

- `~/.arduino15/packages/STM32/hardware/stm32/1.9.0/variants/NUCLEO_F767ZI/variant.h` for Nucleo-144 NUCLEO_F767ZI.
- `~/.arduino15/packages/STM32/hardware/stm32/1.9.0/variants/NUCLEO_L053R8/variant.h` for Nucleo-64 NUCLEO_L053R8.

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz,
theses files must be copied into the corresponding directory:

- `~/.arduino15/packages/STM32/hardware/stm32/x.yy.zz/variants/NUCLEO_F767ZI/variant.h`
- `~/.arduino15/packages/STM32/hardware/stm32/x.yy.zz/variants/NUCLEO_L053R8/variant.h`

---
  
### How to use

This library can be used as a replacement of C++11 STL `std::function`.

For example, we can use `typedef vl::Func<void(void)> THandlerFunction` instead of `typedef std::function<void(void)> THandlerFunction` or `typedef void (*THandlerFunction)(void)`.

Its importance is the ability to be used in complicated function calls, such as private Lambda functions in Classes.

For example:

```cpp
class BlynkEthernet
    : public BlynkProtocol<BlynkArduinoClient>
{
    typedef BlynkProtocol<BlynkArduinoClient> Base;
public:

...

private:
    EthernetWebServer *server;
    ...
    
    void startConfigurationMode()
    {
      ...
      if (!server)
        server = new EthernetWebServer;
	        
      if (server)
      {
        server->on("/", [this](){ handleRequest(); });
        server->begin();    
      }
      ...
    }
};

```

---

This [**Functional-Vlpp library**](https://github.com/khoih-prog/Functional-Vlpp) has been used sucessfully in :

1. [ESP8266_AT_WebServer library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/ESP8266_AT_WebServer)
2. [EthernetWebServer library for Arduino, ESP,Teensy, SAM, SAMD, etc. architectures](https://github.com/khoih-prog/EthernetWebServer)
3. [EthernetWebServer_STM32 library for STM32 architectures](https://github.com/khoih-prog/EthernetWebServer_STM32)
4. [Blynk_Esp8266AT_WM library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/Blynk_Esp8266AT_WM)
5. [BlynkEthernet_WM library for Arduino, ESP,Teensy, SAM, SAMD, etc. architectures](https://github.com/khoih-prog/BlynkEthernet_WM)
6. [BlynkEthernet_STM32_WM library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/BlynkEthernet_STM32_WM)
7. [WiFiManager_NINA_Lite library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/WiFiManager_NINA_Lite)
8. [WiFiWebServer library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/WiFiWebServer)

and many more to come.

---

### How to use in your sketch

Just include in your sketch and modify as follows

```cpp
// For this functional-vlpp library
#include <functional-vlpp.h>

// Modify from
//typedef std::function<void(void)> THandlerFunction;
// or
//typedef void (*THandlerFunction)(void);
// to this
typedef vl::Func<void(void)> THandlerFunction;
// That's it

// Keep these the same
void on(const String &uri, THandlerFunction handler);
void on(const String &uri, HTTPMethod method, THandlerFunction fn);
void on(const String &uri, HTTPMethod method, THandlerFunction fn, THandlerFunction ufn);
void addHandler(RequestHandler* handler);
void onNotFound(THandlerFunction fn);  //called when handler is not assigned
void onFileUpload(THandlerFunction fn); //handle file uploads

```
---
---

### Version v1.0.1

1. Add support to and tested working **OK** in other architectures such as **Teensy, SAM, SAMD, stm32, eps8266, esp32** besides AVR.

### Initial Releases v1.0.0

1. Based on and modified from [Marcus Rugger's functional-vlpp library](https://github.com/marcusrugger/functional-vlpp).


---

### Contributions and thanks

1. Based on and modified from [vczh-libraries/Vlpp](https://github.com/vczh-libraries/Vlpp) and [Marcus Rugger functional-vlpp library](https://github.com/marcusrugger/functional-vlpp)

<table>
  <tr>
    <td align="center"><a href="https://github.com/marcusrugger"><img src="https://github.com/marcusrugger.png" width="100px;" alt="marcusrugger"/><br/><sub><b>⭐️ Marcus Rugger</b></sub></a><br/></td>
  </tr> 
</table>

---

### Contributing

If you want to contribute to this project:
- Report bugs and errors
- Ask for enhancements
- Create issues and pull requests
- Tell other people about this library

---

### License

- The library is licensed under [MIT](https://github.com/khoih-prog/Functional-Vlpp/blob/master/LICENSE)

---

### Copyright

Copyright 2020- Khoi Hoang
