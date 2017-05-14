# Keyboards

## Ergodox

* Uses the Docker instructions below to generate a hex file.
* The creates a .hex file that is up-loadable using the teensy software.

## HHKB

* Uses the Docker instructions below.

## Alps64

* Uses the Docker instructions below.

## Clueboard

* Uses the Docker instructions below.

## Whitefox

* Programming through [QMK][4]
  * When using make to build the keymap, the hex will be sent to the root dir.
  * Unfortunately the keyboard _only_ is programmed using a `.bin` file.
  * This `.bin` can be found in the .build folder of the root QMK dir.
  * Use this file with: `dfu-util -D .build/whitefox_braden.bin -S whiteFoxSerial`

## Atreus

* Use QMK to build the keymap and house the keymap.
* Use avrdude to flash the hex file which is found at the QMK repo root.
* There is a trick where the computer shows up under /dev when in programming mode.
  * The keyboard needs to be put into boot loader mode and
  * then tab to the correct item under /dev
* The keyboard will stay in boot loader mode for not a lot of time so it will have to be quick.
* An example command would be: `avrdude -p atmega32u4 -P /dev/tty.usbmodem1421 -c avr109 -U flash:w:atreus62_braden.hex`
* This keyboard has been traded away.

## Dockerized QMK Make

* Create a hex file using the qmk/docker image:
  * `docker run -e keymap=braden -e subproject= -e keyboard=ergodox --rm -v $('pwd'):/qmk:rw edasque/qmk_firmware`
* Click the reset switch on the keyboard
* This command resets the firmware: `dfu-programmer atmega32u4 erase`
* and this command uploads the new firmware: `dfu-programmer atmega32u4 flash fileofyourfirmware.hex`
* Now the keyboard has the updated firmware and can be rebooted by unplugging it and plugging it back in.

## Notes

* HHKB, Ergodox, Planck, Alps64 has been moved to the [QMK Fork of TMK][1]

[1]: https://github.com/qmk/qmk_firmware
[2]: https://www.massdrop.com/buy/the-whitefox-keyboard?quest-mode=open
[3]: http://input.club/configurator
[4]: https://github.com/tmk/whitefox