Just some tweaks I like to do:

Tweak | File | Description
--- | --- | ---
1 | [KeyRemaps](https://github.com/imnotniki/archSetup/tree/main/~/.config/keyboard) | Swap some keys on my keyboard
2 | [Shortcuts XFCE4](https://github.com/imnotniki/archSetup/blob/main/~/.config/xfce4/xfconf/xfce-perchannel-xml/xfce4-keyboard-shortcuts.xml) | My Keyboard shortcuts for XFCE4 DE
3 | [Screenshot Share](https://github.com/imnotniki/archSetup/blob/main/~/.config/xfce4/scripts/screenftp.sh) | Share screenshots using xfce4-screenshooter + FTP Server




Wacom Settings
===
xinput | grep Wacom\
xinput map-to-output {id} DisplayPort-0\
xsetwacom set "Wacom Bamboo Connect Pen stylus" Area 920 575 6440 4025

Keyboard Tweaks
===
Install xev using pacman:
```shell
sudo pacman -S xorg-xev
```

Either copy it from repo or create it using:
```shell
sudo mkdir -p ~/.config/keyboard && sudo touch >> ~/.config/keyboard/.keyRemap
```

Put this into .keyRemap:
```shell
keycode 118 = Prior
keycode 112 = Next
keycode 117 = End
```

Run or add to ~/.xinitrc:
```shell
xmodmap ~/.config/keyboard/.keyRemap
```

To check keycodes use:
```shell
xev | grep -A2 'keycode'
```

OBS Studio + plugins
===

**Use this encoder on obs if u have AMD**
ffmpeg vaapi hvenc

```shell
pamac install flatpak
```
```shell
flatpak install com.obsproject.Studio
```
```shell
flatpak install com.obsproject.Studio.Plugin.GStreamerVaapi
```
