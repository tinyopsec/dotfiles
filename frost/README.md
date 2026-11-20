# nwm + st dotfiles

Personal config for tinyopsec/nwm and tinyopsec/st-patched.

## Compatibility

Plain upstream st will not build with this config.h. The fork adds features this config depends on: alpha transparency, scrollback, and a few patched shortcuts. If you use vanilla st, strip those sections first or expect build errors.

nwm here is unmodified except for the border colors in nwm.h.

## Files

* nwm.h: nwm configuration (borders, gaps, keys, rules)
* config.h: st configuration (font, palette, shortcuts)
* wallpaper.png: wallpaper used in .xinitrc via feh

## Color palette

Backgrounds and borders:

* #2B2623: background
* #4A4038: normal border
* #9CD3E6: selected border and accent
* #A8742F: urgent border
* #F3F3F5: foreground

nwm borders:

* normal: #4A4038
* selected: #9CD3E6
* urgent: #A8742F

st uses the same ramp. Cursor is #9CD3E6. Background #2B2623, foreground #F3F3F5.

## Build

nwm:

    git clone https://github.com/tinyopsec/nwm
    cp nwm.h nwm/nwm.h
    cd nwm
    make X11INC=/usr/include X11LIB=/usr/lib
    sudo make install

st:

    git clone https://github.com/tinyopsec/st-patched
    cp config.h st-patched/config.h
    cd st-patched
    make
    sudo make install

Wallpaper in .xinitrc:

    feh --bg-scale ~/dotfiles/frost/wallpaper.png

## Notes

* Font: DejaVu Sans Mono pixelsize 18
* Terminal transparency: alpha = 0.3
* nwm mod key: Alt (Mod1)
* Terminal: Alt+Return. Launcher: Alt+d. Kill client: Alt+q.
