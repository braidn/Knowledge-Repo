# Infinity Keyboard KLL Notes

### Building A .bin File

1. Navigate to the controller base directory
1. Run: `/kll/path/to/infinity/build.sh`

### Install .bin

1. Press the flash button on the back of the keyboard
1. Run `dfu-util -D name_of_bin.bin` to flash the KB 

### Handy Links

* [Controller][1] used to create a .bin file
* [Language spec][2] for building kll based files
* [Google Doc][3] highlighting more info on building files


[1]: https://github.com/kiibohd/controller
[2]: https://www.overleaf.com/read/zzqbdwqjfwwf
[3]: https://docs.google.com/document/d/13WwRq4NC4a9cUEwcMS7QcomnTu02k9kuBss7Ep5tDBU/edit?pli=1#heading=h.gg6elj8jslj