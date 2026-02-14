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
    - The problem with `netrw`:
        1. Cannot search recursive. I was not able to find how to set the recursive search for files. The command seems weird to execute and no clear one was found. Will try later tomorrow.

7. Updating the config to have the line number config on.
    - I added the following code, that was suggested by GPT:
    ```lua
        vim.opt.number = true --set number
        vim.opt.relativenumber = true --set relativenumber
    ```
    - Also i learnt that `vim` config file path is stored as variable: `$MYVIMRC`. So we can next time directy run `nvim $MYVIMRC` for editing the `init.lua` file.
        - I added some variables in the config file for `fish` so that I can access the config of fish and my notes folder using the variable.
            - I added this to the config of fish - `set -g MYFISHCONFIGFILE "path"`

14-02-2026

7. Installing `Telescope` since the `netrw` will require to manually set the searching for the document. Instead of doing that I want to install the plugin and do the stuff i want to do instead of con figuring the file.
    - Cloning [telescope-repo](git@github.com:nvim-telescope/telescope.nvim.git) into our `~/.local/share/nvim/site/pack/plugins/start` directory.
    - Telescope requires the following:" }
        1. [plenary](git@github.com:nvim-lua/plenary.nvim.git)
        2. [repgrep](git@github.com:BurntSushi/ripgrep.git)
        3. [telescope-native-fzf](git@github.com:nvim-telescope/telescope-fzf-native.nvim.git)
        4. [fd](git@github.com:sharkdp/fd.git) - installed via `pacman`
    - Now the Telescope can be accessed using `:Telescope`.
    - The problem now is that is showing some entries that are not of the current directory. So time for checking if there is a missing configuration from my side.
        - The problem was I was using the `:Telescope` command instead of `:Telescope find_files`. The former opens the meta picker that its own files instead of the currnet directory files. The later is used for searching inside the current directory.
    - Binding the Telescope find_files command with a keyboard shortcut:
        - I want to use the find_files without having to type the entire thing and as a shortcut i added the following command to the nvim config:
            - `vim.keymap.set("n", "<leader>ff", "<cmd>Telescope find_files<cr>", { desc = "Project files" } end)`
                - This added a keymap for nvim to execute the `:Telescope find_files` command when the keys are pressed in normal mode (n).
                - The leader is the leader key is a special key used for creating custom user defined keymaps.
                - To set the leader key i added this to the config: `vim.g.mapleader = " "` and `vim.g.maplocalleader = "\\"`. Now the leader key is space key.

8. Now we install a directory explorer:
    - Installing [nvim-tree](git@github.com:nvim-tree/nvim-tree.lua.git)
    - Adding the following to nvim config:
        ```lua
            -- Disable loading netrw
            vim.g.loaded_netrw = 1
            vim.g.loaded_netrwPlugin = 1

            -- To require the nvim-tree
            vim.opt.termguicolors = true
            require("nvim-tree").setup({})

            -- To map to the shortcut of space + e to toggle it
            vim.keymap.set("n", "<leader>e", "<cmd>NvimTreeToggle<cr>")

        ```
    - Configuring nvim-tree to auto focus the file that is opened or active in another buffer.
        ```lua
        -- To open nvim tree when vim starts
        vim.api.nvim_create_autocmd("VimEnter", {
                callback = function()
                require("nvim-tree.api").tree.open()
                end,
                })

        -- optionally enable 24-bit colour
        vim.opt.termguicolors = true
        require("nvim-tree").setup({
            update_focused_file = {
            enable = true,
            update_root = false,
            },
        })

        ```
    - Now files active are focused in nvim-tree.

9. Now to install plugins for development
    - Require to work on the following frameworks and languages
        - Languages - 
            1. CPP
            2. C
            3. C#
            4. Javascript
        - Frameworks - 
            1. dotnet
            2. React.JS
            3. Angular.JS
        - Tools required -
            1. Debuggers
            2. Linters
            3. Intellisense
            4. Github Copilot
            5. Obisidian plugin for nvim
    - The main componenet for programming is the syntax understanding by the editor. 
        - The NVIM comes with a LSP (Language Server Protocol) for understanding the syntax.

10. LSP of nvim:
    - LSP is of two types client and server, the client LSP comes wiht nvim, but the server one is required to be a third party. So we will have to install a LSP server and cofig it for our requirements.
    - Lets start with LSP For C#:
        - [omnisharp](git@github.com:OmniSharp/omnisharp-vim.git)
        - [ale](git@github.com:dense-analysis/ale.git) - for linting
            - Installed in `nvim/site/pack/plugins/git-plugins/start` that did not register it to the nvim so moved it to the plugins folder as where all are installed.           

11. Using no package manager is kind of getting very messy and most plugins recommend using one to install their app, and so i have installed lazyvim again. Defeating the entire purpose of removing it. But it taking too much damn time and i want create not configure.
