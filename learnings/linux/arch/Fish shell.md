### Installation of fish shell on my arch

- Reason for installing fish - 
  - Looks cool.

- Things to do to integrate with current setup:
  1. Install fish
    - Command to install `fish`: `sudo pacman -S fish`
  2. Update kitty config to use fish as default shell.
    - `kitty.conf` inside `.confg/kitty/`
    - adding the line to set shell: `shell fish`
      - `fish` will be resolved using `$PATH`
  3. Use shell

- > [!NOTE]
> This is not a system-wide setup, this is just for kitty, so kitty will launch `fish` instead of its default setup. To setup check the section below.

- Other ways to setup default shell
  1. [system-wide](https://wiki.archlinux.org/title/Command-line_shell#Changing_your_default_shell)

