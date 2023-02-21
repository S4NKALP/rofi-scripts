### Rofi for Everything

* Rofi configuration files and scripts for
  - Music Control
  - Wifi Connections  
  - Mounting/Unmounting USB/Partitions
  - Mounting/Unmounting Android devices
  - Screenshots
  - Launcher


|![img](https://github.com/niraj998/niraj998/blob/main/assets/Rofi/Music.png)|![img](https://github.com/niraj998/niraj998/blob/main/assets/Rofi/Wifi.png)|
|-|-|
|![img](https://github.com/niraj998/niraj998/blob/main/assets/Rofi/USBmount.png)|![img](https://github.com/niraj998/niraj998/blob/main/assets/Rofi/AndroidMount.png)|
|![img](https://github.com/niraj998/niraj998/blob/main/assets/Rofi/Screens.png)|![img](https://github.com/niraj998/niraj998/blob/main/assets/Rofi/Screenshot.png)|
|![img](https://github.com/niraj998/niraj998/blob/main/assets/Rofi/Launcher.png)|

## Installation
Clone this repository
```
$ git clone https://github.com/S4NKALP/scripts.git && cd scripts
```

Backup your rofi configs. 
```
$ mkdir -pv ~/.config/rofibkp
$ mv ~/.config/rofi ~/.config/rofibkp
```
Install fonts (Choose any one you like)
Note: There are 2-3 versions of Material design fonts. Just make sure to only have the one I've put in fonts folder. 
  - System-wide
```
$ sudo cp -r ./fonts /usr/share/fonts/
$ fc-cache -fv
```
  - User only
```
$ [ -d "$HOME/.local/share/fonts" ] || mkdir -pv $HOME/.local/share/fonts
$ cp -r ./fonts $HOME/.local/share/fonts
$ fc-cache -fv
```

Install Dependencies
  - for Arch 
```
$ yay -Sy rofi maim simple-mtpfs fuse2 xclip --needed
```
  - Rofi Configs made in Rofi version 1.7.2 (Rofi configs might not work in older version of rofi)
  - All of these packages available in official repository except simple-mtpfs.

Copy scripts and rofi configs
```
$ [ -d "$HOME/.config/rofi" ] || mkdir -pv $HOME/.config/rofi
$ cp -r ./rofi $HOME/.config
```
Enjoy

## How to
- Launch scripts
  - For Launcher run **`rofi -show drun`**
  - For rest of things just run script inside respective folders.
- Colorscheme/Theme
  - All the Colors are coming from style.rasi file inside themes folder for all the rofi configs. Edit style file to change colors.

## More about scripts

#### Screenshot :
  - Takes Screenshot using maim.
  - Saves Screenshots in ~/Pictures/Screenshots.
  - Configure screenshot save location in script.

#### Wifi :
  - Reads /sys/class/net/wl* files to get current status.
  - Uses nmcli for everything else.

#### USB mounting :
  - Default mount location is /mnt, you can change this foler in script.
  - If you don't want to mount to /mnt type name of the folder and it'll create folder inside /mnt and mount in that folder.
  - if you already have askpass setup uncomment askpass line in the script. There's rofi script inside that folder using that for sudo password while mounting.

#### Android mounting :
  - Requires simple-mtpfs and fuse2.
  - it's Setup to mount devices in ~/Cell, you can give your own location in the script.

#### Manage Dual Screens :
  - add your own script to refresh wallpaper / bar or window manager in script. 

### Notes and Todo.
 - Adding more useful things, themes and colors.
 - Pull Requests, Issues, Fork, Contributions are welcome.
 - Keybinding script for sxhkdrc
