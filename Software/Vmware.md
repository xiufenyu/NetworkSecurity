	1. Get back Mouse Cursor: **Ctrl + Alt** 

 
	2. Enable copy-paste texts
	$ sudo apt-get install open-vm-tools
	$ sudo apt-get install open-vm-tools-desktop
	$ reboot

 
	3. Drag-Drop is not working
	$ sudo nano /etc/gdm3/custom.conf
	# Disable Wayland
