# Keyboards

## Ergodox

* Uses the Docker instructions below to generate a hex file.
* The creates a .hex file that is up-loadable using the teensy software.

## HHKB

* Uses the Docker instructions below.

## Alps64

* Uses the Docker instructions below.
  * The controller on this board is a `atmega32u2` and not the u4 variant

## HotDox

* Uses the Docker instructions below.

## Whitefox

* Building .bin's at the moment is a little tricky with the current QMK makefile.
* To get around these issues:
  * Start a docker container: `docker run -d -t -i -e subproject='' -v $('pwd'):/qmk:rw jackhumbert/qmk_firmware bash`
  * Attach to the newly running container.
  * run: `make whitefox-braden-whitefox-braden.bin`  
  * Exit from the container and run the dfu-util command
* Programming through [QMK][4]
  * When using make to build the keymap, the hex will be sent to the root dir.
  * Unfortunately the keyboard _only_ is programmed using a `.bin` file.
  * This `.bin` can be found in the .build folder of the root QMK dir.
  * Use this file with: `dfu-util -D .build/whitefox_braden.bin -S whiteFoxSerial`

## Dockerized QMK Make

* Create a hex file using the qmk/docker image:
  * `docker run -e keymap=braden -e subproject= -e keyboard=ergodox --rm -v $('pwd'):/qmk:rw edasque/qmk_firmware`
* Click the reset switch on the keyboard
* This command resets the firmware: `dfu-programmer atmega32u4 erase`
* and this command uploads the new firmware: `dfu-programmer atmega32u4 flash fileofyourfirmware.hex`
* Now the keyboard has the updated firmware and can be rebooted by unplugging it and plugging it back in.

## Notes

* All keyboards have been moved to the [QMK Fork of TMK][1]

[1]: https://github.com/qmk/qmk_firmware
[2]: https://www.massdrop.com/buy/the-whitefox-keyboard?quest-mode=open
[3]: http://input.club/configurator
[4]: https://github.com/tmk/whitefox
[docker]: http://localhost:4567/KeyboardProgramming#dockerized-qmk-make
