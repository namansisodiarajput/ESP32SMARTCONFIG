# ESP32SMARTCONFIG
dynamically update wifi credentials through app without hardcoded it.


we use WiFi class to connect to a WiFi network "WiFi.begin(ssid, password)". Here we use "hard-coded" ssid and password. It is really inconvenient when we bring our ESP32 to another WiFi network, we have to modify ssid and password according to new network, recompile and flash new code. So there is a technique to overcome this called "SmartConfig".


Now this technique was also applied for ESP32. In order to do SmartConfig, you need a smartphone or tablet (Android or iOS) that connected to WiFi network (which you want ESP32 to connect to) and installed a special application. On this application, you just supply the ssid and password of WiFi network so that the application can use, encode them and then broadcast (via UDP) encoded ssid and password (under packet format) over the air. At this moment, ESP32 with a special software in it will capture these packets, decode back ssid and password and use them to connect to Wifi network. After connecting to WiFi ESP32 will use mDNS to multicast a message to the application to notify that it connected to WiFi.


Application link on playstore -: https://play.google.com/store/apps/details?id=com.cmmakerclub.iot.esptouch



