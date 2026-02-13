#### NVim commands - 

1. Copy to clipboard - `"+y`

### Configuring NVim for my workflow.

A brief history:

- Installed Lazyvim and used it for almost a monnth but it was too much for me. I had little time to learn all teh key maps and it was taking too much time so I kep using vscode for development.

- Today i.e 12-02-2026 I have uninstalled the lazyvim configuration for nvim. And this note is being written with no plugin vanilla nvim.

- Hopefully writing my own config and keymaps will make it possible for me to use nvim instead of vscode for [[dotnet]] developement.

- Step by step what i am doing rn-

12-02-2026:

1. Created a directory in .config directory, `nvim`.
    - Basically the `init.lua` config files are stored here for `Unix` based systems. So naturally create the directory and the file here.
    - The directory information provided in - [nvim-wiki](https://neovim.io/doc/user/starting.html#config).
    - There can be either `init.lua` or `init.vim` in that directory both are supported.
    - Nvim will run this file when it starts.

2. Created the `init.lua` file and added a print statement as follows - `print("hello from init.lua")`.
    - The message disappers immediately, so to check the output executed - `:messages` in nvim. With that confirmed the init script is executed by nvim.

3. Adding a module to file.
    - Adding another lua file but in directory `lua` on the same level of `init.lua` and using `require("module_name")` in `init.lua`. 
    - The above makes `nvim` load the module file. It is basically like importing another script file.
    - The scripts in `lua` folder can be directly imported without requring to mention the path, they are automatically searched. 
        - `init.lua` acts as the starting point of that directory, so if a directory inside the `lua` folder includes a `init.lua` then `require("directory_name")` will call the `init.lua` inside of the directory. Cool.

4. Adding `one-dark` theme for nvim.
    - The [one-dark]( git@github.com : navarasu/onedark.nvim.git]) is what i wanted to install.
    - Since there is no package manager installed, we are going to use the pre-installed one. So it basically adds all the plugins for nvim that are inside the directory: `~/.local/share/nvim/site/pack/plugins/start`.
        - Correction it does not use them directly, they have to added in the config files.
    - Git cloning inside that directory for the one-dark theme, using `git pull git@github.com:navarasu/onedark.nvim.git`
    - I now tried launching `nvim` but the theme was not installed. So lets add the config for it:
        - Now I have to add a config in the `init.lua` for loading it. So 
        ```lua
            require('onedark').setup {
                style = 'darker'
            }
            require('onedark').load()
        ```
    - The font used in the image of `one-dark` is called `Dank Mono`. The theme as plugin does not provide it. So next step is to install the font. As it is cool.

5. To install fonts in arch the best way is to use `pacman` it can install fonts like it install packages, but the font that I want to install is not available in the repository. So I have to install it manually.
    - Following the guide in the link [font-installation-on-arch](https://linuxgenie.net/how-to-install-fonts-on-arch-linux)
    - So after downloading the dank font from - [dank-git](https://github.com/saifulapm/my-fonts/tree/main/Dank%20Mono). And placing it in the directory `use/local/share/fonts/`. And clearing the `font-cache` using the command - `sudo fc-cache -vf`.
    - The font is now installed as it is present in the list presented by the command `fc-list | grep -i 'dank'`.
    - Now to add it to `nvim`.
        - We dont have to add it `nvim`, we can just add it to the terminal and all set, for all the applications using it.
        - So for that we have to update the `kitty.config` file. So inside the [[Kitty]] cofig file therewe can just add `font_family family 'Dank Mono'` and all set.

13-02-2026

6. Adding a file tree explorer.
    - How does the default directory explorer work in `nvim`?
        - Nvim comes with a file explorer called as `netrw`.
        - The `netrw` is a basic file explorer that can allow for searching the directory using the normal vim motion and search from command line.
        - I believe that this could be enough for me as I do not need a very special kind of filter of files and neither do I require the quick access of files. Not so speedy yet. So no installation for any file explorer.
    - How do i use the pre-installed `netrw` for directory exploration?
        - To open a directory just run `nvim .` and the explorer will show all the files.
        - To open it while editing a file use `:Ex` and all set.

7. Now `Telescope`. Or a simpler version of it.

