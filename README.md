This is a fork of Crypter's i2s library for driving 74HC595 shift regesters with DMA from an esp8266. 
I have re-purposed it to 
1. Support more than 4 74HC595 chips
2. Drive led array displays driven from 74HC595 chips with:
*  Fast refresh rate
*  DMA
*  Individual LED dimming/brightness controll 

*This library is still unfinished, but should be finished soon. This message will be removed when it is complete.

# Origional Readme:
Get 32 outputs from ESP8266 boards using shift registers and I2S

What this library can do:
* digitalWrite
* analogWrite (aka. PWM)
* DSWrite (Delta-Sigma PWM)
* servoWrite (servo control signal)
* LEDWrite (Delta-Sigma PWM, exponentialy scalled for realistic LED light output - 127 really looks like half the light of 255)

...and all of that on DMA using timed interrupts for better precision. This means the CPU is mostly free for other uses.

You have sinceTimer and resetTimer functions inbuild for easier timing manipulation.

Soon I'll add wiring diagram, this should suffice for now:
* GPIO2 (NodeMCU pin D4) [i2s output ws] <=> latch (74HC595 pin 12)
* GPIO15 (NodeMCU pin D8) [i2s output clock] <=> serial clock in (74HC595 pin 11)
* GPIO3 (NodeMCU pin RX) [i2s output data] <=> serial data in (74HC595 pin 14)


This library still needs a lot of improvements and optimisations, the current version was good enough for the internet.
If you find a bug please report it, or even better - contribute a fix!

Idea taken from [Cnlohr's LED driver](https://github.com/cnlohr/esp8266ws2812i2s) and [Lhartmann's RepRap driver](https://github.com/lhartmann/esp8266_reprap).

