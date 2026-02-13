## Installation and updates of vs code on arch

- There are more than one way of installation of vs code on arch linux. Three to be exact as mentioned in the arch [wiki](https://wiki.archlinux.org/title/Visual_Studio_Code|wiki)
- My personal installation has been the AUR version which is proprietary microsoft version.

- Here are the exact steps i followed to install vs code:

1. Install `base-devel` using pacman
- `base-devel` contains the required tools like `gcc`, `makepkg` etc that are required to build tools from source.
  - Command - `sudo pacman -S base-devel`

2. Install `git`
- `git` is a version control system that can be used to store all version of our code. It is also useful to access github repositories where the visual studio code is stored.
    - Command - `sudo pacman -S git`

3. Pull the source code of vs code
- The official vs code source code is available on - `https://aur.archlinux.org/visual-studio-code-bin.git`
- To get the code in our system we do the following
  - Command - `git pull https://aur.archlinux.org/visual-studio-code-bin.git`
- Now we have the source available in the directory - 'visual-studio-code-bin'. Lets access it
  - Command - `cd visual-studio-code-bin`
- Now you can see the source code of vs code in the directory. We need to compile this code into a working application. We do that by
  - Command - `makepkg -si`
    - `makepkg` is a tool that compile packages.

4. Now vs code is installed in our system and can be accessed via command `code` in the terminal or via GUI as per your configuration.

## Updating the existing AUR installation of vs code


1. Go to your git pull directory where you got the vs code source pulled.
2. Do `git pull` to get the latest version of the code
3. `makepkg -si` to install the latest version.


### Update History

- 12-02-2026
	- VS code notification that the current version has issues with Copilot so update it.