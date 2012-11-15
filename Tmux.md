All of the above are done with the binding key:

* `tmux attach` will grab an active session
* `tmux att -t SessionName` to grab a specific section
* `tmux ls` to view all active sessions
* `d` to detach from the current session
* `$` to rename current session
* `s` to list sessions while in tmux
* `"` to split a horizontal pane
  * `%` to split a vertical pane
  * `alt arrowKey` to resize current pane
  * `arrowKey` to jump from pane to pane
  * `{` to rotate panes
* `c` to create a new window (think tabs)
  * `,` to rename current window
* `number` or `n` or `p` to cycle the windows
* `[` to jump into visual mode (great for scrolling through buffers and
  such
  * `space` to start selection `enter` to confirm the copy (move around
    like in vim
  * `]` to paste the selected into whatever
