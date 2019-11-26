[root@lvm vagrant]#
[root@lvm vagrant]#
[root@lvm vagrant]#
[root@lvm vagrant]#
######################################################## 
# смотрим название Volume Group
[root@lvm vagrant]# vgs
  VG         #PV #LV #SN Attr   VSize   VFree
  VolGroup00   1   2   0 wz--n- <38.97g    0
########################################################
# переименовываем группу 
[root@lvm vagrant]# history
    1  vgs
    2  vgrename VolGroup00 VolGroupHI
[root@lvm vagrant]# vgs
  VG         #PV #LV #SN Attr   VSize   VFree
  VolGroupHI   1   2   0 wz--n- <38.97g    0

#########################################################
# меняем группу в загрузчике.
vi /etc/fstab
vi  /etc/default/grub
nano /boot/grub2/grub.cfg
# Пересоздаем initrd image, чтобý он знал новое название Volume Group
mkinitrd -f -v /boot/initramfs-$(uname -r).img $(uname -r)  
   
######################################################   
#   перегружаемся
####################################################
***********************************************************
# Добавить модуль в initrd Пингвина
# создаем свою папку 
mkdir /usr/lib/dracut/modules.d/01test
   15  [root@lvm vagrant]#
   16  cd /usr/lib/dracut/modules.d/01test/
 # создаем 2 скрипта
   17  vi module-setup.sh
   18  vi test.sh
 # выдаем права на запуск
   19  cmod +x *
   20  chmod +x *
   21  ls -l
 # пересобираем образ initrd  
   22   mkinitrd -f -v /boot/initramfs-$(uname -r).img $(uname -r)
   23  lsinitrd -m /boot/initramfs-$(uname -r).img | grep test
   24  halt
   #############################################
   пингвин отправлен в чат
   

