[![Foo](https://img.shields.io/badge/Version-1.10-brightgreen.svg?style=flat-square)](#versions)
[![Foo](https://img.shields.io/badge/Website-AlexGyver.ru-blue.svg?style=flat-square)](https://alexgyver.ru/)
[![Foo](https://img.shields.io/badge/%E2%82%BD$%E2%82%AC%20%D0%9D%D0%B0%20%D0%BF%D0%B8%D0%B2%D0%BE-%D1%81%20%D1%80%D1%8B%D0%B1%D0%BA%D0%BE%D0%B9-orange.svg?style=flat-square)](https://alexgyver.ru/support_alex/)

[![Foo](https://img.shields.io/badge/README-ENGLISH-brightgreen.svg?style=for-the-badge)](https://github-com.translate.goog/GyverLibs/GyverUART?_x_tr_sl=ru&_x_tr_tl=en)  

[![Foo](https://img.shields.io/badge/ПОДПИСАТЬСЯ-НА%20ОБНОВЛЕНИЯ-brightgreen.svg?style=social&logo=telegram&color=blue)](https://t.me/GyverLibs)


# GyverUART
Лёгкая библиотека для работы с последовательным портом
- Практически полный аналог Serial, но гораздо легче

### Совместимость
Совместима со всеми Arduino платформами (используются Arduino-функции)

## Содержание
- [Установка](#install)
- [Инициализация](#init)
- [Использование](#usage)
- [Пример](#example)
- [Версии](#versions)
- [Баги и обратная связь](#feedback)

<a id="install"></a>
## Установка
- Библиотеку можно найти по названию **GyverUART** и установить через менеджер библиотек в:
    - Arduino IDE
    - Arduino IDE v2
    - PlatformIO
- [Скачать библиотеку](https://github.com/GyverLibs/GyverUART/archive/refs/heads/main.zip) .zip архивом для ручной установки:
    - Распаковать и положить в *C:\Program Files (x86)\Arduino\libraries* (Windows x64)
    - Распаковать и положить в *C:\Program Files\Arduino\libraries* (Windows x32)
    - Распаковать и положить в *Документы/Arduino/libraries/*
    - (Arduino IDE) автоматическая установка из .zip: *Скетч/Подключить библиотеку/Добавить .ZIP библиотеку…* и указать скачанный архив
- Читай более подробную инструкцию по установке библиотек [здесь](https://alexgyver.ru/arduino-first/#%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0_%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA)
### Обновление
- Рекомендую всегда обновлять библиотеку: в новых версиях исправляются ошибки и баги, а также проводится оптимизация и добавляются новые фичи
- Через менеджер библиотек IDE: найти библиотеку как при установке и нажать "Обновить"
- Вручную: **удалить папку со старой версией**, а затем положить на её место новую. "Замену" делать нельзя: иногда в новых версиях удаляются файлы, которые останутся при замене и могут привести к ошибкам!


<a id="init"></a>
## Инициализация
Нет

<a id="usage"></a>
## Использование
Как у Serial

<a id="example"></a>
## Пример
Остальные примеры смотри в **examples**!
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
## Версии
- v1.2 - добавлен циклический буфер
- v1.3 - поправлен вывод float и добавлен вывод с базисом
- v1.4 - либа собрана в класс, добавлена readStringUntil
- v1.5 - добавлен буфер на отправку и flush
- v1.6 - ускорена запись и чтение
- v1.7 - чуть оптимизирован код
- v1.8 - пофикшен write (спасибо eugenebartosh)
- v1.9 - пофикшен write + оптимизация + поддержка USART0 atmega2560 (by Siliverst)
- v1.10 - вывод переведён на Print.h. Размер стал чуть больше, но будет меньше при работе с другими либами на Print.h

<a id="feedback"></a>
## Баги и обратная связь
При нахождении багов создавайте **Issue**, а лучше сразу пишите на почту [alex@alexgyver.ru](mailto:alex@alexgyver.ru)  
Библиотека открыта для доработки и ваших **Pull Request**'ов!


При сообщении о багах или некорректной работе библиотеки нужно обязательно указывать:
- Версия библиотеки
- Какой используется МК
- Версия SDK (для ESP)
- Версия Arduino IDE
- Корректно ли работают ли встроенные примеры, в которых используются функции и конструкции, приводящие к багу в вашем коде
- Какой код загружался, какая работа от него ожидалась и как он работает в реальности
- В идеале приложить минимальный код, в котором наблюдается баг. Не полотно из тысячи строк, а минимальный код
