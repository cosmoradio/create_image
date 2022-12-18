
Create uncompressed sparse image file from internal eMMC and save to flash drive
sudo dd if=/dev/mmcblk0 bs=1M status=progress | cp --sparse=always /dev/stdin /media/ubuntu/usbdata/ubuntu.img

Extract uncompressed image file to internal eMMC
sudo dd if=/media/ubuntu/usbdata/ubuntu.img of=/dev/mmcblk0 bs=1M status=progress

Create compressed image file from internal eMMC and save to Desktop
sudo dd if=/dev/mmcblk0 bs=1M status=progress | gzip > /home/user/Desktop/ubuntu.img.gz

Extract compressed image file to internal eMMC
sudo gzip -cd /home/user/Desktop/ubuntu.img.gz | dd of=/dev/mmcblk0 bs=1M status=progress
