# TFT_ST7735
New version tested and works with ESP8266. I just discovered that ST7735 cannot work at high SPI speeds so if you downloaded older version of this library and not work, just open library settings and change 80Mhx to 65Mhz and will work, sorry again for being so stupid to publish something never tested on this processor but I was trusting the code and I was really surprised when discover that was faulty in some way.<br><br>
A fast driver that works with any Arduino 8 bit, AVR, DUE, Teensy's (all), ESP8266, SPARK

This version it's completely recoded and it's almost equal to my very popular TFT_ILI9163C library, same features, same speed, same commands! It uses my LPGO Font rendering and it's fully SPI Transaction compatible (when applicable).
This is the FIRST beta, only tested succesfully with Teensy 3.2.<br>

<b>FEATURES:</b><br>
- Very fast
- Same features of TFT_ILI9163C library, same commands.
- Uses LPGO Font Rendering.
- Compatible with many CPU's (see list at the bottom)
- Fully SPI Transaction compatible.
- Fully featured set of commands, it's almost impossible you won't find what you'll need!
- Lot of examples.<br>

<b>About Display and connections:</b><br>
My display it's 1.8" 128*160 buy from ebay, RED pcb and has a SD card (that needssome modification if you want to use with Hi speed SPI or never work!).<br>
My display has 3v3 regulator onboard and works at 5V but signal level are still at 3V3! You are warned! Never connect directly to Arduino or any 5V CPU or you will destroy it! You need a Level Converter chip like CD4050.<br>
The Backlight led need a resistor, I've used a 150R connected to 5V but you need to be sure about yours or you will destroy the backlight and your screen will not be useable so pay EXTRA ATTENTION TO THIS!!!<br>
The RST it's optional, I've connected trough a 10K resistor to +3v3.<br><br>

<b>Connections:</b><br>
Display -> CPU<br>
LED: 150R to 220R (depends of display) connected to VCC<br>
SCK: SPI SCLK<br>
SDA: MOSI<br>
A0: RS<br>
RESET: 10Kohm to +3V3<br>
CS: SS<br>
GND: GND<br>
VCC: If you have a regulator on display connect to 5V<br><br>

<b>CPU's compatible:</b><br>
- Teensy 3.0 (can use also alternative SPI pins!)
- Teensy 3.1 (can use also alternative SPI pins!)
- Teensy 3.2 (can use also alternative SPI pins!)
- Teensy LC (can use also alternative SPI pins!)
- Any arduino 8bit (UNO,etc.)
- DUE
- ESP8266
- SPARK (from next version)<br>

<b>What about SD card holder:</b><br>
I know you will ask so before run to solder and connect it please read this!<br>
On 8 bit AVR you probably can use it but this only because you are running at very low SPI speed. With High speed CPU things are totally different, the chinese vendor always solder resistors or (worst) capacitors on SD card holder SPI lines, this cause problems in the SPI bus and result are unexpected, SD most of the time don't work and cause problems even on display side!<br>
So what?<br>
Buy a trusted high quality SD holder (not from chinese where High Quality it's still an unknown word) and connect very near CPU with smallest cable you can, SD have weak signal!<br>
Do NOT trust SD card holder with level changer chip mounted on (sometime passed as high quality buffers!), these buffers/level converter destroy literally your SPI waveforms and cause many problems on SPI bus, they are designed for slow AVR<br>
The best SD holder has no resitors, capacitor (ok, just one on supply it's ok) or whatever.<br>
Use always REAL branded SD cards and high speed ones (level 10 and up).<br>
It's possible modify the SD holder mounted on display? Probably yes, have to try, maybe I will write a wiki about it one day<br>