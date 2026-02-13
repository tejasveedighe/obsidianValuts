---
tags:
  - linux-tools
---

---
- Window manager are used for creating and managing the graphical user interface. They are responsible for creating the windows like UI, and are installed and configured separately.
- Each window manager is called a X Window Manager. Since they follow X Window System. They are widely used in linux OS. Their are also window manger from [[Wayland]].
- So there are window managers of two types based on the display server protcols. - 
	- [X-Org]
	- [Wayland].
- The archlinux page categorizes the window managers into different type based on their functionality -
	A. Stacking - Traditional windows like.
	B. Tiling - Not letting the windows get overlapped and stacked in the screen with different sizes.
	C. Dynamic - Combines both.

---
- My current installation 
	- Date - 02/01/2026
	- GNOME window manager with [[Wayland]] compositor.
	- Commands used - 
		- `echo $DESKTOP_SESSION`
		- `echo $XDG_CURRENT_DESKTOP`
		- `wmctrl -m`