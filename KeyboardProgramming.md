# Keyboards

## Ergodox

* creating a keymap: `make braden`
* to clean directory: `make clean`
* The creates a .hex file that is up-loadable using the teensy software.

## HHKB

* creating a keymap: `make braden dfu` 
* cleaning: `Makefile clean`
* The dfu option will auto upload the keymap to the keyboard
* The switch to put the keyboard into boot loader mode is where the dip switch used to be.

## Alps64

* Use DFU when making the hex file will upload the keymap on success.
* The PCB has a reset switch at the bottom and is used to put the keyboard in programming mod

## Whitefox

* [Recently purchased][2] 65% board from matt3o
* Programming either done through the [input.club][3] or [TMK][4]

## Atreus

* Use QMK to build the keymap and house the keymap.
* Use avrdude to flash the hex file which is found at the QMK repo root.
* There is a trick where the computer shows up under /dev when in programming mode.
  * The keyboard needs to be put into boot loader mode and
  * then tab to the correct item under /dev
* The keyboard will stay in boot loader mode for not a lot of time so it will have to be quick.
* An example command would be: `avrdude -p atmega32u4 -P /dev/tty.usbmodem1421 -c avr109 -U flash:w:atreus62_braden.hex`

## Notes

* HHKB, Ergodox, Planck, Alps64 has been moved to the [QMK Fork of TMK][1]

[1]: https://github.com/jackhumbert/qmk_firmware
[2]: https://www.massdrop.com/buy/the-whitefox-keyboard?quest-mode=open
[3]: http://input.club/configurator
[4]: https://github.com/tmk/whitefox