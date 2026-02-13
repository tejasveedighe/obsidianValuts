
---
- I update the waybar config file and understood how to bar is customized.
- Waybar config located at - `~/.config/waybar`
	- File is `config` or `config.jsonc`
- Waybar has default config at - `/etc/xdg/waybar`
	- This directory contains the styles and config that are defaulted.
- Added the following to add the workspace icons on the right left side of waybar - 
```json
{
	modules-left: [
		"hyprland/workspaces",
		...
  	]

  "hyprland/workspaces": {
	 "disable-scroll": true,
	 "all-outputs": true,
	 "warp-on-scroll": false,
	 "format": "{name}: {icon}",
	 "format-icons": {
	   "1": "",
	   "2": "",
	   "3": "",
	   "4": "",
	   "5": "",
	   "urgent": "",
	   "focused": "",
	   "default": ""
	 }
   },
}  
```

- The workspace config is copied from the default version with `sway/workspaces` replaced with `hyprland/workspaces` to get it working.