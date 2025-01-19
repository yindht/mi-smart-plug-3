# mi-smart-plug-3
Mi Smart Plug 3(WiFi) install tasmota firmware.  

Hardware info:  
CPU:ESP32C3  
Module:MHCWB6S-B  Flash:4MB
https://manuals.plus/zh-CN/xiaomi/mhcwb6s-b-2-4ghz-wifi-bluetooth-dual-mode-module-manual  
![mi-plug-3 module pinout](https://github.com/yindht/mi-smart-plug-3/blob/main/doc/module_pin.png)

PowerChip:KP15052（5V）  ASM117(3.3V)  
ADC:BL0942  
Relay:hf32fv-16/5hctf590  

GPIO  
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
