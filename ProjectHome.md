The PicoDuino  is an ATtiny85 based microcontroller development board similar to the Arduino line, only cheaper, smaller, and a bit less powerful.
With the ability to use the familiar Arduino IDE the PicoDuino is a great way to jump into electronics, or perfect for when an Arduino is too big or too much.
Preloaded micronucleus tiny85 bottolader and demo app.

Specifications:
-Support for the Arduino IDE 1.0 and later (OS X, Windows, and Linux)
-Built-in USB
-5 I/O pins (2 are used for USB only if your program actively communicates over USB, otherwise you can use all 5 even if you are programming via USB)
> or 6 I/O pins if you dissable reset fuse
-8 KB flash memory (about 6 KB after bootloader)
-I2C and SPI (vis USI)
-PWM on 3 pins (more possible with software PWM)
-ADC on 4 pins
-Power LED
-RGB led
-Reset Button or user readable I/O if you dissable reset fuse
-Keyboard or other HID devices emulation (mouse, gamepad ...)

Differences to DigiSpark:

- Not support shields (integrating RGB shield, you can direct connect I2C LCD module)
- Does not have On-board 500 mA 5V Regulator, USB power only !

+ On-board RGB led
+ On-board user/reset  button
+ can solder reliable metalic USB connector
+ reset is enabled you can program this board with USBASP or Arduino via ISP
+ slim design
+ board can be covered by transparent or white heat shrink tube

Differences to Arduino:

1. The PicoDuino  is powered by an Atmel Attiny85 MCU - this has many differences from an Arduino's ATmega328 and some libraries may not work correctly on it.
2. The PicoDuino  only has about 6 KB of flash memory for storing your code.
3. Pin 3 and Pin 4 (P3 and P4) are used for USB communication and programming, while you can use them in your circuit if you are not using USB communication, you may have to unplug your circuit during programming if the circuit would impede the pin states or dramatically affect the voltage levels on these pins.
4. Pin 3 (P3) has a 1.5k pull-up resistor attached to it which is required for when P3 and P4 are used for USB communication (including programming). Your design may need to take into account that you'd have to overpower this to pull this pin low.
5. The PicoDuino  does not have a hardware serial port nor a hardware serial to USB converter. An example library (DigiUSB) is provided, as well as some example code and a serial monitor like program, but communication with the computer will not always be plug and play, especially when other libraries are involved.


The PicoDuino supports all features found in the IDE with the exception of the serial monitor and the burn bootloader functionality.

Many existing libraries will not work with the Picoduino:
For I2C devices check out the TinyWireM library, which makes it super simple to port an I2C based device library over to use with the PicoDuino.

For example Digispark libraries:
TinyWireM, Usb, Tiny RTC lib, TinyPinChange, SoftSerial
SoftPuseOut, SoftPulseIn, SimpleServo, RGB, RCseq, Mouse
LPD8806, LCD, Keyboard, Joystick, Nunchuk, VirtualWire, OneWire
TinySoftPwm

Pin outs:

All pins can be used as Digital I/O
Pin 0 → I2C SDA, PWM
Pin 1 → PWM
Pin 2 → I2C SCK, Analog
Pin 3 → Analog In (also used for USB+ when USB is in use)
Pin 4 → PWM, Analog (also used for USB- when USB is in use)
Pin 5 → Analog In, default dissabled, only for RESET


Connecting and Programming:

digistump.com/wiki/digispark/tutorials/connecting

More info:
code.google.com/p/picoduino/


If the computer will not recognize the PicoDuino try the following:

Try connecting it to another USB port or system.
Try connecting it to the rear ports (if a desktop)
Try connecting it to a USB hub.
Try a powered USB hub.
If all fails you can upload only via USBASP or Arduino uno ...

If it won't upload, check:

In IDE select
Tools->Board->Digispark
Tools->Programmer->Digispark



A N D   M O R E




You can upload Little Wire firmware and you can:

- usbtiny compatable AVR programmer in minimal form factor with all through hole components
- Computer controllable (via USB) additional features:
> - 4 channel digital input / output
> - ADC with 10 bit resolution
> - 2 paralel hardware PWM outputs
> - 3 paralel software PWM outputs (with v1.1 firmware)
> - SPI interface
> - I2C interface
> - 1 Wire interface (with v1.1 firmware)
> - Pic24f programmer with limited device support (with v1.1 firmware)
- Includes onboard serial bootloader for firmware upgrades!
- You can use it for “Printf style debugging over AVR-ISP pins!”
- USB to UART converter , by loading an other firmware (CDC-232 port)

Possible usages

- AVR programming /summon captainObvious
- LED dimming, color mixing
- General servo driving
- Pan and tilt servo control of a webcam for face tracking
- With additional motor driver IC, 2 wheel robot driving
- Analog voltage recording and plotting
- Controlling LED matrix displays by using SPI module to drive shift registers
- USB to SPI bridge
- USB to I2C bridge
- USB to UART bridge
- General purpose V-USB developement board

More info:
littlewire.cc/

You can upload Simple SD Audio wav Player firmware:

More info:
elm-chan.org/works/sd8p/report.html


You can upload Wavetable Melody Generator firmware:

More info:
elm-chan.org/works/mxb/report.html