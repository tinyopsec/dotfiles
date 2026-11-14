# nwm + st dotfiles

Personal config for [tinyopsec/nwm](https://github.com/tinyopsec/nwm) and [tinyopsec/st-patched](https://github.com/tinyopsec/st-patched).

## Compatibility

Plain upstream `st` will not build with this `config.h`. The fork adds features this config depends on: alpha transparency, scrollback, and a few patched shortcuts. If you use vanilla `st`, strip those sections first or expect build errors.

nwm here is unmodified except for the border colors in `nwm.h`.

## Files

- `nwm.h` - nwm configuration (borders, gaps, keys, rules)
- `config.h` - st configuration (font, palette, shortcuts)
- `wallpaper.png` - wallpaper used in `.xinitrc` via `feh --bg-scale`

## Color palette

Backgrounds and borders:

- `#1A0D08` - background / normal border
- `#3B1A10` - dark brown
- `#6B2E1A`
- `#9C4A2B`
- `#C9703F` - selected border / accent
- `#E8A76A`
- `#F5D08A` - urgent border / light accent
- `#ffffff`

nwm borders:

- normal: `#3B1A10`
- selected: `#C9703F`
- urgent: `#F5D08A`

st uses the same 16-color ramp plus `#ffffff` as bright white.

## Build

nwm:

```
git clone https://github.com/tinyopsec/nwm
cp nwm.h nwm/nwm.h
cd nwm
make X11INC=/usr/include X11LIB=/usr/lib
sudo make install
```

st:

```
git clone https://github.com/tinyopsec/st-patched
cp config.h st-patched/config.h
cd st-patched
make
sudo make install
```

Wallpaper in `.xinitrc`:

```
feh --bg-scale ~/dotfiles/ember/wallpaper.png
```

## Notes

- Font: `Liberation Mono:pixelsize=15`
- Terminal transparency: `alpha = 0.5`
- nwm mod key: Super (Mod4)
- Terminal: Super+Return. Launcher: Super+d. Kill client: Super+q.
