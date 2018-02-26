# FlyingRaspberry

## Installer Raspbian sur raspberry without any GUI

```sh
curl https://downloads.raspberrypi.org/raspbian_lite_latest
```
We need to see the name of the sd card
```sh
lsblk 
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0   1,8T  0 disk 
├─sda1   8:1    0   500M  0 part 
├─sda2   8:2    0 488,7G  0 part 
├─sda3   8:3    0     1K  0 part 
├─sda5   8:5    0 931,3G  0 part /media/keldaan/69d0161c-67c8-4685-8dce-df31ce7a
├─sda6   8:6    0 434,6G  0 part /
└─sda7   8:7    0     8G  0 part [SWAP]
sdb      8:16   1  14,9G  0 disk 
└─sdb1   8:17   1  14,9G  0 part /media/keldaan/3231-3438
```

Thats the last 

Here we need to unmount the mountpoint
```sh
sudo umount /dev/sdb1
```

Then we copy the image file to the sd card 
```
sudo dd bs=4M if=/home/keldaan/Téléchargements/2017-11-29-raspbian-stretch-lite.img of=/dev/sdb1 conv=fsync
```

