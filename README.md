# wmgo
wmgo is a dmenu-based launcher for EWMH compatible window 
managers like awesome wm, XMonad, OpenBox, or i3.

wmgo offers two main features:
* Switching to currently opened windows via matching
  the window's title
* Executing desktop files or binaries in $PATH via
  matching the filename

XDG desktop files and binaries are cached for fast 
startup times of the launcher.

### Usage
By opening wmgo and starting to type, wmgo finds all 
opened windows and applications which include the 
entered substring in their window title or filename.
Pressing enter will either switch to the opened 
window or start the application.

Obligatory screenshot after launching wmgo and typing `mn`:
![Screenshot](http://i.imgur.com/ZruYtmT.png)

### Configuration
The appearance of wmgo can be customized via 
the shell variables 
* `$FONT` to set the font of dmenu
* `$DMENU_OPTIONS` to set the remaining dmenu parameters
   (foreground color, background color, etc.)

For instance,
```bash
FONT="Liberation Mono-8" DMENU_OPTIONS="-b" wmgo
```
would launch wmgo at the bottom of the screen with font 
Liberation Mono in font size 8. Please note that some 
fonts require [dmenu with Xft support](http://tools.suckless.org/dmenu/patches/xft).
Alternatively, the configuration variables can be set
in the file `$HOME/.config/wmgo/config` which 
is sourced at the start of wmgo.
```bash
FONT="Liberation Mono-8"
DMENU_OPTIONS="-b"
```
### Dependencies
wmgo requires the following programms
* [dmenu](http://tools.suckless.org/dmenu/) 
  (optional [dmenu with Xft support](http://tools.suckless.org/dmenu/patches/xft)
  for antialiased fonts etc.)
* [wmctrl](http://tomas.styblo.name/wmctrl/)
* [bash](http://www.gnu.org/software/bash/)

### Example for Awesome WM
First, add keybindings in `rc.lua` to launch wmgo, e.g.
```lua
awful.key({ modkey }, ",", function() exec("/usr/bin/wmgo", false) end)
```
Next, reload your configuration. Now, you can switch between opened windows
or launch new applications via `Mod4 + ,` and starting to type.
