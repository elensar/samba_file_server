# smb.conf Explanation

~~~shell
[users]
  path = /samba/users
  browseable = yes
  read only = no
  force create mode = 0660
  force directory mode = 2770
  valid users = @sambashare @sadmin

[josh]
  path = /samba/josh
  browseable = no
  read only = no
  force create mode = 0660
  force directory mode = 2770
  valid users = josh @sadmin
~~~

### The options have the following meanings
- `[users]` and `[josh]` - The names of the shares that you will use when logging in.
- `path`  - The path to the share.
- `browseable` - Whether the share should be listed in the available shares list. By setting to `no` other users will not be able to see the share.
- `read only` - Whether the users specified in the `valid users` list are able to write to this share.
- `force create mode` - Sets the permissions for the newly created files in this share.
- `force directory mode` - Sets the permissions for the newly created directories in this share.
- `valid users` - A list of users and groups that are allowed to access the share. Groups are prefixed with the `@` symbol.

----------------------

### Common Global Settings for the smb.conf File
`workgroup` = The name of the workgroup or domain.  
`server string` = The comment that describes the server.  
`hosts allow` = Lets you limit access to the Samba server to the IP addresses
listed. If a partial IP address is listed (for example, 192.168.1),
it is treated as a subnet.  
`guest ok` = Specify Yes to allow guest access.  
`guest account` = Specifies the Linux account to be used.  
`security` = Specifies the security mode: Domain, Server, Share, or
User.

Located after the global section is a section for each share that begins with the [sharename] line. The settings in these groups specify the details of a share, such as the comment and path. The following table lists the settings that you can specify for a share.

### Share Settings for the smb.conf File
`[sharename]` = The name used by the share.  
`path=path` = The path to the directory to be shared.  
`comment=comment` = A description of the shared resource.  
`guest ok` = Specify Yes to allow guest access.  
`writeonly` = Specify Yes for read/write, No for read-only.  
`browseable` = Specify Yes to make the share visible in My Network
Places.  
`valid users` = A list of users who can access the share.  
`hosts allow` = Lets you limit access to the Samba server to the IP addresses
listed. If a partial IP address is listed (for example, 192.168.1),
it’s treated as a subnet.

## References
- https://www.dummies.com/programming/networking/network-administration-samba-smb-conf-file/
- https://linuxize.com/post/how-to-install-and-configure-samba-on-ubuntu-18-04/
