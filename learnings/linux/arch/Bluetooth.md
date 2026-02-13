### Bluetooth in arch linux

- I want to use my Bluetooth pods with linux.

- Brief commands that i followed in order:
1. Install `bluez` and `bluez-utils`
2. Checking if the `btusb` kernel module is running, if not then start it using `modeprobe btusb`.
3. Start the `bluetooth.service` using `systemctl start bluetooth.service`
4. Installed `bluetui` for using terminal to control bluetooth.

- So far it does not work. The bluetooth device is not visible on the tui. Check what the device id is and then try later.
