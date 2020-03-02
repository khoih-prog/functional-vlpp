## functional-vlpp Library

[![arduino-library-badge](https://www.ardu-badge.com/badge/functional-vlpp.svg?)](https://www.ardu-badge.com/functional-vlpp)

The original [vczh-libraries/Vlpp](https://github.com/vczh-libraries/Vlpp) provides common C++ construction, including string operation / generic container / linq, function templates to better support ***C++ functional programming across platforms***. 

The `functional portion` of the project was then forked and modified to be used for Arduino by [Marcus Rugger functional-vlpp library](https://github.com/marcusrugger/functional-vlpp). 

This library is forked, modified to use and tested working ***OK*** in other architectures such as ***Teensy, SAM, SAMD, stm32, eps8266, esp32***.

### Installation

The suggested way to install is to:

#### Use Arduino Library Manager
Another way is to use `Arduino Library Manager`. Search for `functional-vlpp`, then select / install the latest version. Uo can also use this link [![arduino-library-badge](https://www.ardu-badge.com/badge/functional-vlpp.svg?)](https://www.ardu-badge.com/functional-vlpp) for more detailed instructions.

#### Manual Install

1. Navigate to [functional-vlpp](https://github.com/khoih-prog/functional-vlpp) page.
2. Download the latest release `functional-vlpp-master.zip`.
3. Extract the zip file to `functional-vlpp-master` directory 
4. Copy whole 
  - `functional-vlpp-master/src` folder to Arduino libraries' directory such as `~/Arduino/libraries/`.
  
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

This library has been used sucessfully in :

1. [ESP8266_AT_WebServer library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/ESP8266_AT_WebServer)
2. [EthernetWebServer library for Arduino, ESP,Teensy, SAM, SAMD, etc. architectures](https://github.com/khoih-prog/EthernetWebServer)
3. [EthernetWebServer_STM32 library for STM32 architectures](https://github.com/khoih-prog/EthernetWebServer_STM32)
4. [Blynk_Esp8266AT_WM library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/Blynk_Esp8266AT_WM)
5. [BlynkEthernet_WM library for Arduino, ESP,Teensy, SAM, SAMD, etc. architectures](https://github.com/khoih-prog/BlynkEthernet_WM)
6. [BlynkEthernet_STM32_WM library for Arduino, Teensy, SAM, SAMD, STM32, etc. architectures](https://github.com/khoih-prog/BlynkEthernet_STM32_WM)

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
  
### Contributions and thanks
1. Forked from [vczh-libraries/Vlpp](https://github.com/vczh-libraries/Vlpp) and [Marcus Rugger functional-vlpp library](https://github.com/marcusrugger/functional-vlpp)

### Contributing

If you want to contribute to this project:
- Report bugs and errors
- Ask for enhancements
- Create issues and pull requests
- Tell other people about this library

### Copyright

Copyright 2020- Khoi Hoang
