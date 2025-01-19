# mi-smart-plug-3
Mi Smart Plug 3(WiFi) install tasmota firmware.  

## Hardware
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
 
## Wire connect
connect usb serial (such as CH340) 
CH340   Module  
TXD -> Pin 15#(U0RXD)  
RXD -> Pin 16(U0TXD)  
GND -> Pin 7 or 14 or21 GND  
GND -> pin 9 (IO9 set ESP32 to Download mode) 

It is not easy to open mi-smart plug's shell, it will be broken if you forcefully pry open the shell.
Maybe you can try: Drill some holes on the shell,the location is just on the top of those pins.  

## Flash tasmota firmware  
1.Download firmware from https://ota.tasmota.com/tasmota32/release/  
tasmota32c3.factory.bin  

2.python esptool.py -p COM4 --baud 460800 write_flash 0x0 tasmota32c3.factory.bin  

3.disconnect pin9,reboot mi Plug

now tasmota firmware should work. 

## Tasmota firmware configure 
1.connect mobile or pc to smart plug wifi hotspot.  
2.visit tasmota web ui,and set your home wifi name and password,then reboot 
3.find and smart plug ip,access it by borwser,you can config like this
![mi-plug-3 config](https://github.com/yindht/mi-smart-plug-3/blob/main/doc/tasmota_config.png)
then restart.  
4.now every thing sould work,you can control mi-smart plug 3 in your local home network.  

Enjoy it!