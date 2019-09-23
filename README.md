# Samba file server

Knowledge base for installing and configuration of a Samba server on Raspberry Pi 4.


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


## Using external storages

If you want to use an external storage for your Samba server, please make sure that your Raspberry Pi supports the file system.

If you want to use an storage with NTFS as file system you must add the NTFS support on your Pi:  
`sudo apt-get install ntfs-3g`  
After that, you have to restart the Pi.

If you use NTFS without support, you may can read the data on the storage over the Pi itself but you can't write and trying to call an folder on the storage over Samba will result in an error.


## References

- https://www.raspberrypi.org/magpi/samba-file-server/
- https://www.raspberrypi.org/magpi/build-a-raspberry-pi-nas/
- https://tutorials.ubuntu.com/tutorial/install-and-configure-samba
- https://www.techrepublic.com/article/how-to-set-up-quick-and-easy-file-sharing-with-samba/
- https://linuxize.com/post/how-to-install-and-configure-samba-on-ubuntu-18-04/
