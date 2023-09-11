# kozuka
Compact and nice GBA consolizer.

![prev_](https://github.com/tasseidenki/kozuka/assets/144659973/3dc38346-ab1c-47ff-825d-9f834304680b)

Main features: 
- small footprint;
- full-size HDMI connector;
- Type-C power port (PD-compatible);
- compatible with modern and retro cartridge slots;
- momentary pushbutton on/off;
- backlit power indicator.

PCB preview:

<img width="538" alt="Screenshot 2023-09-11 at 4 12 39 PM" src="https://github.com/tasseidenki/kozuka/assets/144659973/4cd068c3-a6fb-4381-b390-b18445735b8e">

STP preview:

<img width="525" alt="Screenshot 2023-09-11 at 4 35 32 PM" src="https://github.com/tasseidenki/kozuka/assets/144659973/4d5cdfb1-621d-4c8e-8c7f-d643e5d0a3e3">

To build this, you need:
- a GBA or GBA SP, preferably with a broken screen, for salvaging its CPU, SRAM, Link port, cartridge connector (optional) and chokes.

A few more things:
- SpartanEdge Accelerator board (https://wiki.seeedstudio.com/Spartan-Edge-Accelerator-Board);
- SNES controller connector, preferably with 90' pins (https://www.aliexpress.com/item/32991018800.html)
- KY002L flip-flop switch (https://www.aliexpress.com/item/32955392643.html)
- AtMega 328p-au (or another Arduino-compatible MCU with enough memory) and a 16M oscillator, TC26H works best;
- Vertical momentary pushbutton (13 mm);
- Ribbon HDMI cable (male + female) (https://www.aliexpress.com/item/1005003777630816.html type A2/A3, A4);
- TLV71325 2.5V SOT23-5 LDO;
- 0805 Resistors: 100k x 3, 15R, 18K, 1k x 2, 47R x 2, 330R x 4, 270R, 5k1 x 2.
- 0805 Capacitors: 100n x 14, 10u x 2, 100p x 3, 30p x 2, 
- 6-pin Type-C connector;
- common SOD123 diode x 3;
- 5x 1206 LED (optional - backlight) and 3mm (power on) LED;
- 2.54 mm pins (long and short);
- MicroSD card.

How-to (main steps):
1. Configure the slide switch selectors of the SpartanEdge to "boot from SD card". 
2. Solder the components as directed on the PCB(s), sandwich in the SpartanEdge.
3. Format your MicroSD card as FAT32 and drop the latest bitstream https://github.com/zwenergy/gbaHD/tree/master/bitstream in its root directory.
4. Flash the latest controller profile onto the m328p, along with the required bootloader: https://github.com/Zekfoo/gbaHD-AIO-Shield/blob/main/controller/controller.ino
Voila!

First demo: Tokyo Game Show 2023, booth 05-N04 (Tassei Denki).
Based on zwenergy's GBAHD project (github.com/zwenergy/gbaHD).
