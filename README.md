# wmgo
wmgo is a dmenu-based launcher for EWMH compatible window 
managers (e.g. awesome wm, XMonad, OpenBox, i3, ...).
wmgo offers two main features:

* Switching to currently opened windows via matching
  the window's title
* Executing desktop files or binaries in $PATH via
  matching the filename

XDG desktop files and binaries are cached for fast 
startup times of the launcher.

### Obligatory Screenshot
(http://i.imgur.com/5t5W1DT.png)

### Dependencies
wmgo requires the following programms
* [dmenu](http://tools.suckless.org/dmenu/)
* [wmctrl](http://tomas.styblo.name/wmctrl/)
* bash
