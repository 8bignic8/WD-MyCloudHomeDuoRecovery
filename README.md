# WD-MyCloudHomeDuoRecovery
Recovery Data for people who killed theyer WD Cloud duo with a Hack. Please don't sue me. I like the Product but I killed it. soooooo

First interesitng Link: 
https://www.mydealz.de/diskussion/guide-wie-installiere-ich-debian-und-openmediavault-auf-meiner-wd-my-cloud-home-1575345

Second interesting Link with Uart recovering:
https://community.wd.com/t/intalling-open-media-vault-alpha-state-finished-there-is-an-easier-method-now-i-keep-the-post-for-research-data/251323?cjevent=8b23b0d4607411ed835765100a18050c&utm_medium=afl1&utm_source=cj&utm_content=Shop+WD+US&cp1=7988170&utm_campaign=USwdhomepage&utm_term=10-28-2021&cp2=digidip

Third interesting Link: 
https://forum.openmediavault.org/index.php?thread/7784-default-login/

Credit @ZeusJan look up Link 3 ^^

````
Commands to copy:
kernel: busybox dd if=Image of=/dev/mmcblk0 seek=50331648 bs=1 conv=notrunc
kernel recovery: busybox dd if=Image of=/dev/mmcblk0 seek=80674816 bs=1 conv=notrunc
Rootfs: busybox dd if=rootfs.bin of=/dev/mmcblk0 seek=35651584 bs=1 conv=notrunc
Rootfs recovery: busybox dd if=rootfs.bin of=/dev/mmcblk0 seek=97452032 bs=1 conv=notrunc

Formating filesystem:
make_ext4fs -L debian /dev/mmcblk0p2
make_ext4fs -L var /dev/mmcblk0p5
make_ext4fs -L usr /dev/mmcblk0p6

create new folder or reuse the existing ones on the /mnt/ folder to mount the 3 partitions, and untar with this command “tar zxf” every file on their corresponding partition:

20-root.tar.gz on mmcblk0p2
21-var.tar.gz on mmcblk0p5
22-usr.tar.gz on mmcblk0p6

````
