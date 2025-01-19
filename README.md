# mi-smart-plug-3
Mi Smart Plug 3(WiFi) install tasmota firmware.  

## Hardware info:  
CPU:ESP32C3  
Module:MHCWB6S-B  Flash:4MB  
https://manuals.plus/zh-CN/xiaomi/mhcwb6s-b-2-4ghz-wifi-bluetooth-dual-mode-module-manual  
![mi-plug-3 module pinout](https://github.com/yindht/mi-smart-plug-3/blob/main/doc/module_pin.png)

PowerChip:KP15052（5V）  ASM117(3.3V)  
ADC:BL0942  
Relay:hf32fv-16/5hctf590 
  

## GPIO
IO10: relay  
IO5: LED1  
IO18:LED2  
IO19:Button  
IO6: RXD(ADC TXD)
IO7: TXD (ADC RXD)

32	Button1	4 x Button
224	Relay1	8 x Relays
288	Led1	4 x Leds
289	Led2	4 x Leds
544	LedLink	Link led
8160	BL0942 Rx	BL0942 Serial interface
  
 
## Flash tasmota firmware 
1.connect usb serial (such as CH340) 
CH340   Module  
TXD -> Pin 15#(U0RXD)  
RXD -> Pin 16(U0TXD)  
GND -> Pin 7 or 14 or21 GND  
GND -> pin 9 (IO9 Download mode)  

2.Download firmware from https://ota.tasmota.com/tasmota32/release/  
tasmota32c3.factory.bin  

3.python esptool.py -p COM4 --baud 460800 write_flash 0x0 tasmota32c3.factory.bin  

4.disconnect pin9,reboot mi Plug

4.now tasmota firmware should work. 
connect to smart plug wifi hotspot ,and visit tasmota web ui,set your home wifi name and password in web ui
then smart plug will reset,then you can config like this
![mi-plug-3 config](https://github.com/yindht/mi-smart-plug-3/blob/main/doc/tasmota_config.png)
then restart.
now every thing sould work,you can control mi-smart plug 3 in your local home network.

enjoy it!