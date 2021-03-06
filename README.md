# Indoor Air Quality monitor
## A cheap, simple and smart indoor air quality monitor based on ESP8266 and a buch of cheap sensor

This is an Arduino SDK project to create an Indoor Air Quality monitor, with MQTT support. With a WeMos D1 mini (ESP8266) and a Bosch BME280 sensor, plus a MQ135 VOCs air detector and a bunch of other components, you can create a fully-featured air quality monitor for your home.

## Features

It's a quite simple project, based on Wemos D1 Mini lite ESP8266 module (bought for few $ on Aliexpress) and Bosch BME280 temp/hum/pressure sensor. There's also a MQ135 VOCs sensor for CO2, buthane and other gasses. All data will be displayed via web:

![Web Gui](https://github.com/michelep/IndoorAirQualityMonitor/raw/master/assets/webgui_1.jpg)

and sent via MQTT to a broker or a gateway for storage and/or visualization (like Grafana).

## Build it!

Board building it's straight forward: just connect BME280 via I2S bus, MQ135 to A0 (via 180KOhm resistor) and an RGB common-anode LED (if you want fading light changing color based on humidex index - very nice but quite useless!) with related resistors.

![Schema](https://github.com/michelep/IndoorAirQualityMonitor/raw/master/assets/schema.jpg)

Then change configuration on config.json fitting your needs, compile and flash firmware and SPIFFS: that's all!

## Configuration

All configurable items are in /data/config.json file, in JSON format. This directory need to be flashed to ESP8266's SPIFFS area. Moreover, you can change configuration via WEB GUI

## Changelog

v0.2.0 - 12.07.2021
- WEB GUI completely rewritten using PureCSS
- MQTT re-engineered for better handling
- Change NTP client library
- More natural LED fading

v0.1.1 - 13.10.2019
- added ota_enable to prevent accidental or unwanted OTA updates (true if OTA is enables, false otherwise)
- change MQTT messages

v0.1.0 - 03.07.2019
- added alarm for temp, humidity, air quality and humixed indexes
- some minor fixes

v0.0.6
- hardware improvements: BME280 
- piezo buzzer

v0.0.5
- Update to ArduinoJson 6
- move from REST to MQTT

v0.0.4
- Added reboot and WiFI RSSI config parameters
- Fixed an error on datetime print

v0.0.3
- Fixed an issue with RestClient object: now will be instantiated only when needed. Removed global object.

v0.0.2
v0.0.1
- First beta releases, not public yet!

## Support

There's no support nor any warranty! USE AT YOUR OWN RISK! But if you need help, try raise an Issue or sending a mail to o-zone@zerozone.it ;-) Of course, you are strongly encouraged to get the code and improve them!
