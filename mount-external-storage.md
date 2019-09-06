# Mount external storage

First check how your external storage is available for the Pi. You can do it with the command `lsblk`.  
![lsblk](/assets/console-lsblk.png)

We will use the usb with the name **64 GB NTFS** as example and mount it to `/media/usbstick`.

~~~shell
sudo mkdir -m 1777 /media/usbstick

lsblk
# sda -> sda1 was the Usb stick

sudo mount -t ntfs /dev/sda1 /media/usbstick/
~~~


After creating and mounting, you have to change the permission for the external storage.  
Change permission for external storage:  
- https://stackoverflow.com/questions/3740152/how-do-i-change-permissions-for-a-folder-and-all-of-its-subfolders-and-files-in
- https://askubuntu.com/questions/90339/how-do-i-set-read-write-permissions-my-hard-drives  
~~~shell
find /media/usbstick/ -type d -exec chmod 777 {} \;
~~~

To unmount the external storage, just enter `sudo umount /media/usbstick` in the Terminal.

References:  
- https://askubuntu.com/questions/285539/detect-and-mount-devices  
