# Infinity Keyboard KLL Notes

### Building A .bin File

1. Navigate to the controller `/build` directory
1. Run: `../kll/path/to/infinity/build.sh`

### Install .bin

1. Press the flash button on the back of the keyboard
1. Run `dfu-util -D name_of_bin.bin` to flash the KB

### Layering

* Layering starts from 0. Meaning all partials begin at index 1.
* There are three ways to change the layer of a keyboard:
  * _layerLatch_: shift the layer in place while held down.
  * _layerLock_: lock the layer in place over the current.
  * _layerShift_: only shift the layer for the next keypress.
* Extra layers are set in the `-DPartialMaps` make flag.
* Each layer is set using the `;` delimiter
  * an example being: `layer1;layer2`
* If there is a space seperating layers they get combined
  * an example being: `layer1 layer1-5;layer2` 
  
### 60% HHKB3 Layout

* Basically the same key structure as a HHKB.
* Function 1 is behind the RShift.
* Function 2 is below the LShift.
* Function 3 is below RShift.
* Function 4 is below Function 1.

### Handy Links

* [Controller][1] used to create a .bin file
* [Language spec][2] for building kll based files
* [Google Doc][3] highlighting more info on building files


[1]: https://github.com/kiibohd/controller
[2]: https://www.overleaf.com/read/zzqbdwqjfwwf
[3]: https://docs.google.com/document/d/13WwRq4NC4a9cUEwcMS7QcomnTu02k9kuBss7Ep5tDBU/edit?pli=1#heading=h.gg6elj8jslj