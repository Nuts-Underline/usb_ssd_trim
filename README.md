# usb_ssd_trim
How to make possible to use trim/discard funtions on SSD connected via USB. As default trim not working in such case, its a long story about ATA, SCSI and USB. 

There set of UDEV rules to enable trim/discard for usb connected SSDs with differnt USB-SATA/NVME controllers (Realtek, VIA, ASM)

file 50-usb-ssd-trim.rules must be placed to /etc/udev/rules.d

then reload udev like 

udevadm control -R -S

or

service udev force-reload

Then 

lsblk --discard <USB SSD dev path>

if DISC-GRAN not equal to zero then trim working, it must be 0 on HDDs

Commits are welcome. Please send only tested VID,PID

Use on own risk only: some USB storage not handle trim correctly, even can be damaged 

tested on my own USB SSD drives 

based on 

https://wiki.gentoo.org/wiki/Discard_over_USB

https://askubuntu.com/questions/262154/trim-and-ssd-with-usb-3-0-enclosure-does-not-work-uasp-not-supported
