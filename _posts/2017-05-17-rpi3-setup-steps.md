---
layout: post
title: PiKeeb_01 - RPi3 initial setup
---
A running list of the actions taken to setup my RPi3 for light dev work - using
a USB keyboard and an Android phone as the screen.
- use NOOBS to install Raspbian Jessie + PIXEL
- create new user
-- give new user `sudo` and `adm` group access
-- add new sudoer permissions into `/etc/sudoers.d` to give my user complete
`sudo` access
--- `visudo -f /etc/sudoers.d/somefilename`
--- `someusername ALL=(ALL) NOPASSWD: ALL` - allows me to sudo without
reauthenticating constantly - may change post setup
--- setup autologin by editing `/etc/lightdm/lightdm.conf`
    autologin-user=someusername
- `apt-get update && apt-get upgrade`
- enable ssh via `rpi-config`
- generate an ssh key
- set git user.name and user.email
- install random stuff via `apt-get`
-- `synaptic` - visual package manager for later on
-- `x11vnc` - vnc server that allows access to main session
- setup for `x11vnc` in a [random comment](https://www.raspberrypi.org/forums/viewtopic.php?p=108862#p108862)
-- `sudo apt-get install x11vnc`
-- `x11vnc -storepasswd`
-- setup autostart config (for headless booting) in
`~/.config/autostart/x11vnc.desktop`
    [Desktop Entry]
    Encoding=UTF-8
    Type=Application
    Name=X11VNC
    Comment=
    Exec=x11vnc -forever -usepw -display :0 -ultrafilexfer
    StartupNotify=false
    Terminal=false
    Hidden=false
-- use `raspi-config` to set default resolution (since we'll be booting without
a real "display" connected)
--- futzed around with `xrandr` but couldn't get it to work. was trying to add
specific resolutions since i'll be using a 16:9 screen and was looking to work
with a small resolution to minimize power spent rendering the screen
-- it just works! with usb tethering on my Android phone and VNCViewer to
connect I get display/mouse/keyboard/internet for my RPi
- vim and neovim
-- neovim
--- dependencies for building locally are well documented in the wiki
--- `time make CMAKE_BUILD_TYPE=Release`
    real    8m25.880s
    user    7m44.660s
    sys     0m16.070s
--- `time make oldtest`
    real    2m34.525s
    user    1m13.570s
    sys     0m8.190s
--- `time LC_ALL=C make test` resulted in a lockup - had to kill the process
-- vim - tried compiling it a few times and troubleshooting the output and gave
up after ~15min


