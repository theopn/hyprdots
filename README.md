# Theo's Hyprland Config

I swear I am not following the hype.
Hyprland just has so many utilities in their "ecosystem," it is essentially a DE configured with text config.

## Installation

Assumes Fedora because I am too old and tired and lazy to distro-hop anymore.

```sh
# Official repository recommends solopasha/hyprland, but as of December 2025, it has been unmaintained
sudo dnf copr enable sdegler/hyprland
sudo dnf install hyprland
sudo dnf install hyprpaper hypridle hyprlock hyprsunset hyprpolkitagent hyprland-qt-support
sudo dnf install dunst rofi waybar

# Install hy3
sudo dnf install aquamarine-devel hyprland-devel
hyprpm update
hyprpm add https://github.com/outfoxxed/hy3

# if stow has not been installed
sudo dnf install stow
cd $HOME
git@github.com:theopn/hyprdots.git
cd hyprdots

stow hypr
stow dunst
stow rofi
stow waybar
```

## XWayland and Fractional Scaling

In my Framework 13 with 2.8k display, I use fractional scaling (1.67).
Out of the box, XWayland application will be hard scaled, make it look pixelated.
The workaround is to disable scaling for XWayland application and create the X11 config file (`~/.Xresources`) with the DPI value.

```sh
# 1.67 * 100
echo "Xft.dpi: 167" > ~/.Xresources
```

