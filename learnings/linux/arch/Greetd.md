
---
Date - 31-01-2026

- Removed Gnome and all its dependencies from the system
- Installed Greetd as [login manager]
- Using the agreety version of greetd for login. It is a simple console based login where input for username and password is taken like the normal shell does when a vanilla arch installed.
- Greetd uses a config file at the location - 
  - `/etc/greetd/config.toml` where the config is saved.
  - the current config from the file contains a minimal setup that tells the `greetd.service` to use the `agreety` as the login manager and run the command `start-hyprland` in the next shell.
  - So we are just launching [hyprland] using the recommended or safe launch command.
