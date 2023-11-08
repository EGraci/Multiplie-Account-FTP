# Installation FTP
```
sudo apt install vsftpd
```
Create file configurate
```
sudo nano /etc/vsftpd.conf
```
File configurate
```
anonymous_enable=NO
local_enable=YES
write_enable=YES
local_umask=022
chroot_local_user=YES
allow_writeable_chroot=YES
pasv_enable=YES
pasv_min_port=40000
pasv_max_port=50000
```

# Restart Server FTP
```
sudo systemctl restart vsftpd
```

# Add User FTP
```
sudo adduser [name user]
```
Setting folder allow acces
```
sudo usermod -d /var/www/[name folder] [name user]
```
Change access folder
```
sudo chown -R www-data:www-data /var/www/[name folder]
sudo find /var/www/[name folder] -type d -exec chmod 775 {} \;
sudo find /var/www/[name folder] -type f -exec chmod 664 {} \;
```
# Show User FTP
```
cut -d: -f1 /etc/passwd
```
# Delete User FTP
<b>Warning Delete Directory Access</b>
```
pkill -u [username]
userdel -r [username] #Warning Delete Directory Access
userdel [username]
```
<b>Don't forget to  Restart Server FTP</b>
