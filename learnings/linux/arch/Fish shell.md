---
id: Fish shell
aliases: []
tags: []
---
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

---

### Configuring fish 
1. Adding path values for quick access:
  - Require to access notes folder and config folder of [[Neovim]]
  ```lua
    set -g MYFISHSHELLCONFIGFILE 'path to the file'
  ```

    - This set my path to the directory and to the files that i want to access quick.
2. Using a alias for nvim  to be opened with vim.
  - Added to code - `alias nvim="vim"` and it works.
3. Now i want to add a shortcut to `shutdown now` of linux command.
    - That is also done using alias.
    - Added the alias - `alias dielinux="shutdown now"`
4. `fish_config` a web based config command to change the config of the shell. Used this to change the color and the prompt to `->` from the default one.

