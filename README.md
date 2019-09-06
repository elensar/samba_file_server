# Samba file server

Knowledge base and configuration for using a Samba server on Raspberry Pi 4.


## Installation

To install a Samba server on Raspbian you only need the package manager `apt-get`.

~~~shell
sudo apt-get update

sudo apt-get upgrade

sudo apt-get install samba samba-common-bin
~~~


## Change config

After installing the Samba server you can directly append your configurations on the config file. In order to use the changes you only have to make a quick restart of the Samba server itself. A system restart is not required.

~~~shell
sudo vi /etc/samba/smb.conf
# open config in VI
# sudo leafpad /etc/samba/smb.conf
# open config in Text Editor

sudo /etc/init.d/smbd restart
# restart Samba server
~~~

You can find a configuration example under [smb.conf](./smb.conf.md) for a quick start. An explanation of how the configuration works and what options are possible can be found on [smb.conf-explanation](./smb.conf-explanation.md).


## Mount storage

If you want to use an external storage, you may need to mount the storage manually. You can find a short documentation under [mount-external-storage](./mount-external-storage.md).


References:  
- https://www.raspberrypi.org/magpi/samba-file-server/
- https://www.raspberrypi.org/magpi/build-a-raspberry-pi-nas/
- https://tutorials.ubuntu.com/tutorial/install-and-configure-samba
- https://www.techrepublic.com/article/how-to-set-up-quick-and-easy-file-sharing-with-samba/
- https://linuxize.com/post/how-to-install-and-configure-samba-on-ubuntu-18-04/
