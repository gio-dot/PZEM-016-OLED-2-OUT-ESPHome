# PZEM-016-OLED-2-OUT-ESPHome

I modified a PZEM-016 putting inside a Wemos D1 mini with ESPHome firmware and an oled display to show relevant readings. PZEM-016 has an rs485 interface, so to connect it to Wemos d1 rs485 chip must be removed and voltage level has to be shifted to 3.3V using two 2k2 resistors. I used A and B pin on the old rs485 connector to create two digital outputs that can be used ie to drive two relais module. 

ESPHome firmware source: [wemos_d1_pzem016_display.yaml](https://github.com/Gio-dot/PZEM-016-OLED-2-OUT-ESPHome/blob/master/wemos_d1_pzem016_display.yaml)

For instructions about ESPHome installation see: https://esphome.io/index.html

## Schematic

<img src="https://github.com/Gio-dot/PZEM-016-OLED-2-OUT-ESPHome/blob/master/img/ESPHome-wemos-d1-pzem016-display_bb.png" width="800">

<p float="left">
  <img src="https://github.com/Gio-dot/PZEM-016-OLED-2-OUT-ESPHome/blob/master/img/IMG_20200429_104740.jpg" width="300" />
  <img src="https://github.com/Gio-dot/PZEM-016-OLED-2-OUT-ESPHome/blob/master/img/IMG_20200429_023520.jpg" width="300" /> 
  <img src="https://github.com/Gio-dot/PZEM-016-OLED-2-OUT-ESPHome/blob/master/img/2020-04-30%2000_55_38-Panoramica%20-%20Home%20Assistant.png" width="300" />
</p>


## ESPHome firmware notes

To use roboto font as in this project, copy Roboto-Regular.ttf file in your ESPHome folder.
- At boot display is always turned on;
- If Out A is ON display still remains on;
- If Out A is OFF display will turn OFF after 30s;
- Total daily energy sensor is included;
- There are 2 sensors set: one fast (updated every 2s for precise total daily energy calculation and fast display refresh) and one slow (every 10s) to be used in Home assistant.
- Diplay can be used to show information from Home assistant; in this example i show status of Climate out.






