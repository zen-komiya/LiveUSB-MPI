# LiveUSB-MPI


### 初めてisoを生成する場合
lb config --mirror-bootstrap "http://ftp.jp.debian.org/debian/"  
lb config --mirror-chroot "http://ftp.jp.debian.org/debian/"  
lb config --mirror-binary "http://ftp.jp.debian.org/debian/"  
lb config -a amd64  
lb config --bootappend-live "boot=live components locales=ja_JP.UTF-8 keyboard-layouts=ja"  
lb config --distribution bookworm  
lb config --archive-areas "main contrib non-free non-free-firmware"   
lb config  
lb build

### 再度isoを生成する場合
lb clean  
lb config  
lb build  

## USBへisoイメージを書き込む
fdisk -l  
dd if=./live-image-amd64.hybrid.iso of=/dev/sdc bs=1048576
