## personal build of dwm
todo list:
- the bar is broken help
- patch in a clean bar, includes
	- time (no more timedatectl)
	- battery level (no more guessing)
	- weather? optional
- add xresources compatibility (for pywal)
- new layouts (grid, attachaside, centered master)
- patches: centered master, cfacts(?), crop windows(?), fibonacci (?), exresize for floating windows, tabs (for monocle mode), flextile(?? lots of reading), gapless grid + horizontal grid, movestack/push (?), rotate stack, save floats (floating aesthetic), sticky, stacker(?) and stackmfact (vertical resizing), three column layout (same as centered master?), xtile (??? lots of reading)

done:
- now uses mononoki nerd font
- gaps patched in, custom binds:
  - alt-super-j to decrease gaps
  - alt-super-k to enlarge gaps
  - alt-super-0 to reset gaps and alt-super-shift-0 to toggle gaps
  - default gaps are a nice aesthetic 25
  - alt-q to close a window
  - alt-enter for new terminal, alt-shift-enter for toggle master
  - alt-tab for next tag, alt-shift-tab for previous tag
  - control-alt-delete to quit (pranking windows users if they find my computer unattended)
- more custom bindings! execute a command on keypress, features implemented: (thank you random reddit man for your code)
  - f1 to play/pause song
  - f2/f3 to dec/inc volume by 3%
  - f4/f5 to dec/inc brightness by 2.5%
  - alt-comma/alt-period to go to prev song/next song
    - it makes sense if you think of it as ncmpcpp binds, comma maps to "<" and period maps to ">"
  - conversely, alt-shift-period/alt-shift-comma to seek forward/backward 3 seconds respectively
  - print screen (prt sc, XK_Print) for instascrot
- patched in swallow, pertag (for swallow to work, change "st" to "St"), shiftview, autostart, ewmh (not entirely sure if it works or not), attach direction (changed position of newly spawned window)
- the bar now displays shulk's monado arts (with Source Han Sans to match the aesthetic)
- everything is blurred  (thanks compton??)
