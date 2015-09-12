# How to Program current Keyboards

## Planck

* create a keymap and upload it: `make KEYMAP=braden COMMON=true`
* to clean directory: `make clean`
* use the `dfu` option at the end of the build command to auto upload

## Ergodox

* creating a keymap: `make -f Makefile.lufa micro`
* to clean directory: `make -f Makefile.lufa clean`
* The creates a .hex file that is up-loadable using the teensy software.

## HHKB

* creating a keymap: `make -f Makefile KEYMAP=name` 
* cleaning: `make -f Makefile clean`
* like the planck, using the `dfu` option to auto upload the image.