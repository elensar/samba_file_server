# smb.conf extensions examples

~~~config
[local]
  comment = Pi shared folder
  path = /home/pi/share
  browseable = yes
  writeable = Yes
  public = no
  guest ok = yes

[usbstick]
  comment = Usb Stick
  path = /media/pi/64 GB NTFS
  browseable = yes
  writeable = yes
  public = no
  guest ok = yes

[multimedia]
  comment = Multimedia storage
  path = /media/pi/2 TB NTFS
  browseable = yes
  writeable = yes
  only guest = no
  public = no
  guest ok = yes

[common]
  comment = Common storage
  path = /media/pi/EC8213D58213A35E
  browseable = yes
  writeable = yes
  only guest = no
  public = no
  guest ok = yes
~~~
