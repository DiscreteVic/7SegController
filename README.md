# 7SegController
Controller to 7-seg display developed at DE10-Lite (Altera MAX10)

Typical problem with DE10-Lite at Ubuntu 20.4:
	
   -Usb Blaster (use USB 2.0)
	Add "51-altera-usbblaster.rules" file at /etc/udev/rules.d/ . content of file:
	
	   SUBSYSTEM=="usb", ATTR{idVendor}=="09fb", ATTR{idProduct}=="6001", MODE="0666"
	   SUBSYSTEM=="usb", ATTR{idVendor}=="09fb", ATTR{idProduct}=="6002", MODE="0666"
	   SUBSYSTEM=="usb", ATTR{idVendor}=="09fb", ATTR{idProduct}=="6003", MODE="0666"
	   SUBSYSTEM=="usb", ATTR{idVendor}=="09fb", ATTR{idProduct}=="6010", MODE="0666"
	   SUBSYSTEM=="usb", ATTR{idVendor}=="09fb", ATTR{idProduct}=="6810", MODE="0666"

If the error remains run:

	   udevadm control --reload 
	   sudo apt-get install libudev1:i386
	   sudo ln -sf /lib/x86_64-linux-gnu/libudev.so.1 /lib/x86_64-linux-gnu/libudev.so.0
	
   -Restart the PC

	   killall jtagd
	   jtagd --user-start
	   jtagconfig
	
