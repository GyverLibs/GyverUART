# GyverUART
Lightweight serial port library
- Almost a complete analogue of Serial, but much easier

### Compatibility
Compatible with all Arduino platforms (using Arduino functions)

## Content
- [Install](#install)
- [Initialization](#init)
- [Usage](#usage)
- [Example](#example)
- [Versions](#versions)
- [Bugs and feedback](#feedback)

<a id="install"></a>
## Installation
- The library can be found by the name **GyverUART** and installed through the library manager in:
    - Arduino IDE
    - Arduino IDE v2
    - PlatformIO
- [Download Library](https://github.com/GyverLibs/GyverUART/archive/refs/heads/main.zip) .zip archive for manual installation:
    - Unzip and put in *C:\Program Files (x86)\Arduino\libraries* (Windows x64)
    - Unzip and put in *C:\Program Files\Arduino\libraries* (Windows x32)
    - Unpack and put in *Documents/Arduino/libraries/*
    - (Arduino IDE) automatic installation from .zip: *Sketch/Include library/Add .ZIP library…* and specify the downloaded archive
- Read more detailed instructions for installing libraries [here] (https://alexgyver.ru/arduino-first/#%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE% D0%B2%D0%BA%D0%B0_%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA)

<a id="init"></a>
## Initialization
Not

<a id="usage"></a>
## Usage
Like Serial

<a id="example"></a>
## Example
Other examplesSee **examples** for cranberries!
```cpp
#include <GyverUART.h>

char data0 = 'b';
int8_t data1 = -50;
uint8_t data2 = 125;
int16_t data3 = -2000;
uint16_t data4 = 30000;
int32_t data5 = -70000;
uint32_t data6 = 4194967295;
float data7 = 3681.65424;
float data8 = -4375.12353;
String data9 = "LOL LOL";

const char *data10[] = {
  "LOL"
  "KEK",
  CHEBUREK,
};

byte data11 = 0b11101011;
uint32_t data12 = 0xFAB666;

void setup() {
  uart.begin();
  uart.println(data0);
  uart.println(data1);
  uart.println(data2);
  uart.println(data3);
  uart.println(data4);
  uart.println(data5);
  uart.println(data6);
  uart.println(data7);
  uart.println(data8, 3);
  uart.println(data9);
  uart.println("KEK KEK");
  uart.println(F("KEK KEK MACRO"));
  uart.println(data10[2]);
  uart.println(data11, BIN);
  uart.println(data12, HEX);
}

void loop() {
}
```

<a id="versions"></a>
## Versions
- v1.2 - added circular buffer
- v1.3 - fixed float output and added output with basis
- v1.4 - either collected into a class, readStringUntil added
- v1.5 - added buffer for sending and flush
- v1.6 - faster writing and reading
- v1.7 - slightly optimized code
- v1.8 - fixed write (thanks eugenebartosh)
- v1.9 - fixed write + optimization + support for USART0 atmega2560 (by Siliverst)
- v1.10 - output translated to Print.h. The size has become slightly larger, but will be smaller when working with other libs on Print.h

<a id="feedback"></a>
## Bugs and feedback
When you find bugs, create an **Issue**, or better, immediately write to the mail [alex@alexgyver.ru](mailto:alex@alexgyver.ru)
The library is open for revision and your **Pull Request**'s!