# Keyboards

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

## Alps64

* Impending, Alps keyboard from HASU

## B.Face

* Impending, ISO layout 60% From Winkeyless
* This will use the Bootmapper Client software over TMK/QMK

## Plate TKL

* PCB yet to decided. Either an old Phantom(TMK) or B.87

## Whitefox

* [Recently purchased][2] 65% board from matt3o
* Programming either done through the [input.club][3] or [TMK][4]

## Notes

* HHKB, Ergodox, Planck, Alps64 has been moved to the [QMK Fork of TMK][1]

[1]: https://github.com/jackhumbert/qmk_firmware
[2]: https://www.massdrop.com/buy/the-whitefox-keyboard?quest-mode=open
[3]: http://input.club/configurator
[4]: https://github.com/tmk/whitefox