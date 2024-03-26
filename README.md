# usb_ssd_trim
set of UDEV rules to enable trim/discard for usb connected SSDs with differnt USB-SATA/NVME controllers (Realtek, VIA, ASM)

Use on own risk only: some USB storage not handle trim correctly, even can be damaged 

tested on my own USB SSD drives 

based on https://wiki.gentoo.org/wiki/Discard_over_USB

file 50-usb-ssd-trim.rules must be placed to /etc/udev/rules.d

then reload udev like 

udevadm control -R -S

or

service udev force-reload
