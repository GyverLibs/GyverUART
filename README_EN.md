This is an automatic translation and may be incorrect in some places. See the source README and examples for authoritative information.

[![latest](https://img.shields.io/github/v/release/GyverLibs/GyverUART.svg?color=brightgreen)](https://github.com/GyverLibs/GyverUART/releases/latest/download/GyverUART.zip)
[![PIO](https://badges.registry.platformio.org/packages/gyverlibs/library/GyverUART.svg)](https://registry.platformio.org/libraries/gyverlibs/GyverUART)
[![Foo](https://img.shields.io/badge/Website-AlexGyver.ru-blue.svg?style=flat-square)](https://alexgyver.ru/)
[![Foo](https://img.shields.io/badge/%E2%82%BD%24%E2%82%AC%20%D0%9F%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D1%82%D1%8C-%D0%B0%D0%B2%D1%82%D0%BE%D1%80%D0%B0-orange.svg?style=flat-square)](https://alexgyver.ru/support_alex/)
[![Foo](https://img.shields.io/badge/README-ENGLISH-blueviolet.svg?style=flat-square)](https://github-com.translate.goog/GyverLibs/GyverUART?_x_tr_sl=ru&_x_tr_tl=en)  

[![Foo](https://img.shields.io/badge/ПОДПИСАТЬСЯ-НА%20ОБНОВЛЕНИЯ-brightgreen.svg?style=social&logo=telegram&color=blue)](https://t.me/GyverLibs)

# GyverUART
Easy library to work with serial port
- Almost complete analogue of Serial, but much easier

### Compatibility
ATmega328 and others from this generation

## Contents
- [Installation](#install)
- [Initialization](#init)
- [Use of use](#usage)
- [Example](#example)
- [Versions](#versions)
- [Bugs and feedback](#feedback)

<a id="install"></a>
## Installation
- The library can be found under the name **GyverUART** and installed through the library manager in:
    - Arduino IDE
    - Arduino IDE v2
    - PlatformIO
- [Download the library](https://github.com/GyverLibs/GyverUART/archive/refs/heads/main.zip).zip archive for manual installation:
    - Unpack and put in *C:\Program Files (x86)\Arduino\libraries* (Windows x64)
    - Unpack and put in *C:\Program Files\Arduino\libraries* (Windows x32)
    - Unpack and put in *Documents/Arduino/libraries/ *
    - (Arduino IDE) Automatic installation from .zip: *Sketch/Connect library/Add .ZIP library...* and specify downloaded archive
- Read more detailed instructions for installing libraries[here](https://alexgyver.ru/arduino-first/#%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0_%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA)
### Update
- I recommend always updating the library: new versions fix errors and bugs, as well as optimize and add new features.
- Through the library manager IDE: find the library as when installing and click "Update"
- Manually: **Delete the folder with the old version** and then put the new one in its place. “Replacement” can not be done: sometimes new versions delete files that will remain when replaced and can lead to errors!

<a id="init"></a>
## Initialization
No.

<a id="usage"></a>
## Use of use
Like Serial.

<a id="example"></a>
## Example
For more examples see **examples**!
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
  "LOL",
  "KEK",
  "CHEBUREK",
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
- v1.2 - cyclic buffer added
- v1.3 - corrected float output and added base output
- v1.4 - Liba collected in class, readStringUntil added
- v1.5 - Buffer for sending and flush added
- v1.6 - Recording and reading accelerated
- v1.7 - slightly optimized code
- v1.8 - Fixed write (thank you eugenebartosh)
- v1.9 - Fixed write + optimization + support USART0 atmega2560 (by Siliverst)
- v1.10 - output translated to Print.h. The size is slightly larger, but will be smaller when working with other libs on Print. h h

<a id="feedback"></a>
## Bugs and feedback
If you find bugs, create **Issue**, or better write to the mail immediately.[alex@alexgyver.ru](mailto:alex@alexgyver.ru)  
The library is open for revision and your **Pull Requests*!

When reporting bugs or incorrect work of the library, it is necessary to specify:
- Library version
- What is used by the IC
- SDK version (for ESP)
- Arduino IDE version
- Are embedded examples that use features and designs that cause bugs in your code working correctly?
- What code was downloaded, what work was expected from it and how it works in reality
- Ideally, attach the minimum code in which the bug is observed. Not a canvas of a thousand lines, but a minimum code.
