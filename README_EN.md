This is an automatic translation, may be incorrect in some places. See sources and examples!

# Gyveruart
Light library for working with a sequential port
- almost a complete analogue of Serial, but much easier

## compatibility
Atmega328 and other from this generation

## Content
- [installation] (# Install)
- [initialization] (#init)
- [use] (#usage)
- [Example] (# Example)
- [versions] (#varsions)
- [bugs and feedback] (#fedback)

<a id="install"> </a>
## Installation
- The library can be found by the name ** gyveruart ** and installed through the library manager in:
    - Arduino ide
    - Arduino ide v2
    - Platformio
- [download the library] (https://github.com/gyverlibs/gyvert/archive/refs/heads/main.zip). Zip archive for manual installation:
    - unpack and put in * C: \ Program Files (X86) \ Arduino \ Libraries * (Windows X64)
    - unpack and put in * C: \ Program Files \ Arduino \ Libraries * (Windows X32)
    - unpack and put in *documents/arduino/libraries/ *
    - (Arduino id) Automatic installation from. Zip: * sketch/connect the library/add .Zip library ... * and specify downloaded archive
- Read more detailed instructions for installing libraries [here] (https://alexgyver.ru/arduino-first/#%D0%A3%D1%81%D1%82%D0%B0%BD%D0%BE%BE%BE%BED0%B2%D0%BA%D0%B0_%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA)
### Update
- I recommend always updating the library: errors and bugs are corrected in the new versions, as well as optimization and new features are added
- through the IDE library manager: find the library how to install and click "update"
- Manually: ** remove the folder with the old version **, and then put a new one in its place.“Replacement” cannot be done: sometimes in new versions, files that remain when replacing are deleted and can lead to errors!


<a id="init"> </a>
## initialization
No

<a id="usage"> </a>
## Usage
Like Serial

<a id="EXAMPLE"> </a>
## Example
The rest of the examples look at ** Examples **!
`` `CPP
#incLude <gyveruart.h>

char data0 = 'b';
int8_t data1 = -50;
Uint8_t Data2 = 125;
Int16_t Data3 = -2000;
Uint16_t Data4 = 30000;
Int32_T DATA5 = -70000;
Uint32_T DATA6 = 4194967295;
Float Data7 = 3681.65424;
Float Data8 = -4375.12353;
String Data9 = "Lol Lol";

const char *DATA10 [] = {{
  "Lol",
  "Kek",
  "Cheburek",
};

Byte data11 = 0b11101011;
Uint32_T DATA12 = 0XFAB666;

VOID setup () {
  uart.begin ();
  UART.PRINTLN (DATA0);
  urt.println (Data1);
  urt.println (Data2);
  UART.PRINTLN (DATA3);
  urt.println (Data4);
  urt.println (Data5);
  urt.println (Data6);
  urt.println (Data7);
  urt.println (Data8, 3);
  UART.PRINTLN (DATA9);
  urt.println ("Kek Kek");
  uart.println (F ("Kek Kek Macro"));
  urt.println (Data10 [2]);
  urt.println (Data11, Bin);
  urt.println (Data12, Hex);
}

VOID loop () {
}
`` `

<a id="versions"> </a>
## versions
- V1.2 - Added cyclic buffer
- V1.3 - The conclusion of Float is corrected and the conclusion with the basis has been added
- V1.4 - Liba is assembled to class, added by ReadStringuntil
- v1.5 - added a buffer for sending and Flush
- V1.6 - Record and reading accelerated
- V1.7 - The code is slightly optimized
- V1.8 - Found Write (thanks to Eugenebartosh)
- V1.9 - Found Write + Optimization + Support USART0 Atmega2560 (By Siliverst)
- V1.10 - The conclusion was transferred to Print.h.The size has become a little larger, but it will be smaller when working with Dcranberries on Print.h

<a id="feedback"> </a>
## bugs and feedback
Create ** Issue ** when you find the bugs, and better immediately write to the mail [alex@alexgyver.ru] (mailto: alex@alexgyver.ru)
The library is open for refinement and your ** pull Request ** 'ow!


When reporting about bugs or incorrect work of the library, it is necessary to indicate:
- The version of the library
- What is MK used
- SDK version (for ESP)
- version of Arduino ide
- whether the built -in examples work correctly, in which the functions and designs are used, leading to a bug in your code
- what code has been loaded, what work was expected from it and how it works in reality
- Ideally, attach the minimum code in which the bug is observed.Not a canvas of a thousand lines, but a minimum code