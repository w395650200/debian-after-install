# Debian after install
## Install intel wifi driver if necessary
```sh
sudo apt-get install firmware-iwlwifi
```
## Config sudo with new file
```sh
visudo -f /etc/sudoers.d/username
```

Add one line:
```sh
username ALL=(ALL) ALL
```
## Chinese language support
For Xfce DE, Chinese fonts installation is required (using Synaptic suggested).

Add the following to the .bashrc file if chinese display is desired:
```sh
export LANG=zh_CN-UTF8
```
_optional_
```sh
sudo dpkg-reconfigure locales
```

## Input method
```sh
sudo apt-get install fcitx fcitx-sunpinyin
```

_optional_
```sh
im-config
```

## Edit "/etc/apt/sources.list"
```sh
deb http://deb.debian.org/debian/ stretch main contrib non-free
deb-src http://deb.debian.org/debian/ stretch main contrib non-free
deb http://security.debian.org/ stretch/updates main contrib non-free
deb http://deb.debian.org/debian/ stretch-updates main contrib non-free
```
## Update
```sh
sudo apt-get update && sudo apt-get upgrade
```
## Perform a quick scan for open ports
```sh
sudo nmap -sS localhost
```
## Enable BBR by adding two lines in /etc/sysctl.conf
```sh
net.core.default_qdisc=fq
net.ipv4.tcp_congestion_control=bbr
```
## Make a firewall

## Install Latex
sudo apt-get install texlive

## Install virtualbox
From offical website suggested

WARNING: The vboxdrv kernel module is not loaded.

FIX: using Synaptic to fix broken packages to solve the independences first.

```sh
sudo apt-get install linux-headers-$(uname -r)
sudo /sbin/vboxconfig
```
## Install Matlab
```sh
sudo mount -t auto -o loop ~/path-to-matlab/Matlab_2016a/R2016a_glnxa64.iso ~/matlab/
```
Create Matlab desktop entry
```sh
[Desktop Entry]
Exec=/usr/local/MATLAB/R2016a/bin/matlab -desktop
Icon=/usr/local/MATLAB/R2016a/toolbox/shared/dastudio/resources/MatlabIcon.png
Terminal=false
StartupNotify=true
```
