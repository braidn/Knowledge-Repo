# NeoVim

### Known Issues

1. For some reason, neovim has an issue with some implementations of xterm and ctrl-h.
A possible fix follows:

```
infocmp $TERM | sed 's/kbs=^[hH]/kbs=\\177/' > $TERM.ti
tic $TERM.ti
```

More info can be found [here][1]

[1]: http://unix.stackexchange.com/questions/180087/why-pressing-ctrl-h-in-xterm-tmux-sends/180106#180106