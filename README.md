# XMousePasteBlock

Listens for middle mouse click events and clears the primary X selection (and cut buffers) on detection to avoid accidentially pasting stuff all over the place.

## About

No need to disable your precious middle mouse button bindings, no clearing of visual selections nor performance losses because of emptying the primary X clipboard periodically.
With the utilization of XInput and Xlibs this has _no_ measurable impact on performance whatsoever.
No elevated privileges required. Just run within your regular users' X session.

## Installation

On Arch Linux you may simply use the [AUR package](https://aur.archlinux.org/packages/xmousepasteblock-git).

For all other distros, please follow the instructions below.

### Dependencies

You might need to install the libev, Xlib and X11 Input extension headers.

Debian and derivatives (e.g. Ubuntu):
```
sudo apt-get install libev-dev libx11-dev libxi-dev
```
Fedora:
```
sudo dnf install libev-devel libX11-devel libXi-devel
```

### Building

Compile and install:
```
make
sudo make install
```

<details>
<summary>Note for OpenBSD users (click to expand)</summary>
Before running <code>make</code>, please uncomment the respective comments
inside the <code>Makefile</code><br>
<br>
</details>

## Running
Just add `xmousepasteblock` to your startup script/config.

Note: If you're using any kind of clipboard manager, make sure your it does not prevent clearing the PRIMARY selection.
E.g. "Klipper" does that by default with the option "Prevent empty clipboard".

## Known issues
Does not support remapped mouse buttons, e.g. via
`xinput set-button-map`
