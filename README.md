[root@lvm vagrant]#
[root@lvm vagrant]#
[root@lvm vagrant]#
[root@lvm vagrant]#
######################################################## 
[root@lvm vagrant]# vgs
  VG         #PV #LV #SN Attr   VSize   VFree
  VolGroupHI   1   2   0 wz--n- <38.97g    0
[root@lvm vagrant]# history
    1  vgs
    2  vgrename VolGroup00 VolGroupHI
    3  vi /etc/fstab
    4  vi /etc/fstab
    5  nano /etc/fstab
    6  vi /etc/fstab
    7  cat /etc/fstab
    8  vi  /etc/default/grub
    9  nano /boot/grub2/grub.cfg
   10  vi /boot/grub2/grub.cfg
   11  mkinitrd -f -v /boot/initramfs-$(uname -r).img $(uname -r)
   12  halt
   13  vgs
   14  mkdir /usr/lib/dracut/modules.d/01test
   15  [root@lvm vagrant]#
   16  cd /usr/lib/dracut/modules.d/01test/
   17  vi module-setup.sh
   18  vi test.sh
   19  cmod +x *
   20  chmod +x *
   21  ls -l
   22   mkinitrd -f -v /boot/initramfs-$(uname -r).img $(uname -r)
   23  lsinitrd -m /boot/initramfs-$(uname -r).img | grep test
   24  halt

