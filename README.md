# Decrypt Keyserver
Decrypts a filesystem with key from ssh-server. Integrated in initramfs

Configure initramfs for networking (/etc/initramfs-tools/initramfs.conf)

> DEVICE=eth0
> IP=[IP]::[GATEWAY]:[NETMASK]:[HOSTNAME]:eth0:off

Where the configured hostname is the keyservers ssh username.


# Install
* Place dropbear private key file to /root/id_dropbear
* Configure known_hosts and nameservers in /usr/share/initramfs-tools/hooks/crypt-keyserver
* Configure keyservers host/ip address in /usr/share/initramfs-tools/scripts/local-top/decrypt
* and fire it up with:

> update-initramfs -u
