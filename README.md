# AsyncTelegram2

Thi library is the successor to the asynctelegram library.
It was chosen to change the name in addition to the major version to mark clearly a breaking point.
AsyncTelegram2 is now no longer tied to the Espressif ESP8266 / ESP32 hardware, but can virtually work with any MCU capable of supporting an SSL connection and with any kind of transport layer like WiFi, Ethernet, GSM module (still to be tested).

___
### Introduction
AsyncTelegram2 is an Arduino class for managing Telegram Bot on embedded system.

Don't you know Telegram bots and how to setup one? Check [this](https://core.telegram.org/bots#6-botfather).

When you add the possibility to send a message from your IoT application to a Telegram Bot, this should be only an additional "features" and not the core of your firmware.
Unfortunately, most of Telegram libraries, stucks your micro while communicating with the Telegram Server in order to read properly the response and parse it.

AsyncTelegram2 do this job in async way and not interfee with the rest of code!

It relies on [ArduinoJson](https://github.com/bblanchon/ArduinoJson) v6 library so, in order to use a AsyncTelegram2 object, you need to install the ArduinoJson library first (you can use library manager).

With Ethernet adapter, but not only, i wold strongly suggest to use this library for secure connection [SSLClient](https://github.com/OPEnSLab-OSU/SSLClient), a BearSSL based library wich is very light and fast. For example, on ESP32 platform the same code with SSLClient against WiFiClientSecure, uses about 30 kb less SRAM and is much faster to re-establish connection to the server thanks to the support of sessions.

+ **this library work with ArduinoJson library V6.x _**


### Features
+ Send and receive non-blocking messages to Telegram bot (also in silent mode - no notification)
+ Send photo both from url and from local filesystem (SPIFFS, LittleFS, FFAT, SD etc etc )
+ Inline keyboards
+ Reply keyboards 
+ Receive localization messages
+ Receive contacts messages 

### To do
+ Send documents

### Supported boards
The library works virtually with any kind of baord capable of SSL connection.

### Simple and responsive usage
Take a look at the examples provided in the [examples folder](https://github.com/cotestatnt/AsyncTelegram2/tree/master/examples).

### Reference
[Here how to use the library](https://github.com/cotestatnt/AsyncTelegram2/blob/master/REFERENCE.md). 

+ 2.0.0   Initial version, most of functionality of AsyncTelegram
