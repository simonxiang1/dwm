## Personal build of dwm window manager

Dwm is a dynamic window manager (dwm) from suckless that dynamically tiles windows based off a master-slave orientation. Vanilla dwm is very bland and doesn't come with very much, so I added some patches for functionality and style.

To install my build of dwm, run
```
git clone https://github.com/simonxiang1/dwm
cd dwm
```
(Optional) Now my build of dwm autostarts compton pointing to my specific configuration file, so of course you'll need to edit this to fit your system. Simply type `vim config.def.h` and search for the word "autostart". Once you find the autostart array, replace my path with the correct path to your compton configuration file (or delete the line altogether).

Also, dwm saves screenshots to a custom directory on my system. To change this, while in the `config.def.h` file search for "scrot" and change the file path, or just delete the command and replace it with `scrot` if you just want to save screenshots to the home directory.

One more thing: you may want to install [polybar-dwm-module](https://github.com/mihirlad55/polybar-dwm-module), since my build of dwm is set up to work with polybar. (You can skip the dwm-specific install instructions, I took care of that for you! But you still need to follow the polybar related ones, or just look in my [dotfiles](https://github.com/simonxiang1/dotfiles/tree/master/.config/polybar).) If you want to use the native bar, set the variable `usealtbar` to 0 in `config.def.h`.

 After you've made your changes, run
```
cp config.def.h config.h
```
(Not optional) Finally, compile dwm by running
```
sudo make install clean
```
Soft dependencies include st, dmenu, mpc, alsa, xbacklight, scrot, polybar, and picom. However, you can easily subsitute these for whatever you like in the config.h file. Make sure to append 'exec dwm' or some variant to your .xinitrc file.

## Features:

- Custom keybindings!
  - Alt-Super-j/Alt-Super-k to decrease/increase gaps
  - Alt-Super-0 to reset gaps and Alt-Super-Shift-0 to toggle gaps
  - Alt-q to close a window
  - Alt-Enter for a new terminal
  - Alt-Shift-Enter to toggle a window in the master area
  - Alt-Tab to view the next tab (workspace), Alt-Shift-Tab to view previous tag
  - Alt-u for centered master, Alt-o for centered floating master
  - F1 to play/pause music (mpd)
  - F2/F3 to decrease/increase volume by 3%
  - F4/F5 to decrease/increase brightness by 2.5%
  - Alt-comma/Alt-period to skip to previous/next song
    - (Think of this as ncmpcpp binds: comma maps to <, period maps to >)
  - Alt-Shift-comma/Alt-Shift-period to seek forward/backward 3 seconds in a song  
  - Print screen key (prt sc, XK_Print) to screenshot (saves to custom folder)
  - Control-Alt-Delete to quit dwm and log out
  - All other binds are dwm default (see man dwm)
- Patches applied:
  - ~~Swallow- floating windows spawned by a terminal consume the useless terminal to save screen real estate~~ goodbye swallow, sane people use dmenu to open things anyway
  - Pertag- each tag saves information about bar status, window type (floating, monocle, etc) to make tags function more like workspaces
  - Shiftview- allows cycling between tags
  - Autostart- will autostart compton and st by default in this build
  - EWMH- doesn't entirely work but should provide support for things like polybar
  - Centered Master- new window layouts
  - Attach Direction- choose where new windows are spawned, by default in this build new windows will spawn from the top in the slave stack
  - ~~The bar displays Shulk's Monado Arts (斬, 疾, 翔, 盾, 撃) instead of the boring "1 2 3 4 5"~~ Now displays black dots
  - !NEW! dwm-anybar and dwm-ipc (see [here](https://github.com/mihirlad55/dwm-anybar) and [here](https://github.com/mihirlad55/dwm-ipc) respectively) have been patched in! This means we have very functional polybar support, provided you use [polybar-dwm-module](https://github.com/mihirlad55/polybar-dwm-module)

#### Notes:
- There are ~~lots of~~ _no_ issues regarding the bar in my build of dwm	
  - ~~Notably, polybar doesn't start properly~~ yay
  - ~~The dwm bar doesn't display any information on the right with xsetroot~~ fixed with polybar
  - ~~I would like for it to display the time, battery level, and maybe weather~~ fixed with polybar
  - ~~Considering patching dwm-ipc and polybar-dwm-module~~ done
- ~~Xresources compatibility means recompiling dwm on each color scheme switch~~ fixed with polybar
  - ~~To make this work like intended, I would have to find a way to have dwm recompile without logging out~~ fixed with polybar
  - ~~Then I would have to run this each time I run "newtheme", which is a pain~~ fixed with polybar

Pull requests welcome!
