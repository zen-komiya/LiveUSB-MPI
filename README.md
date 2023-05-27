# LiveUSB-MPI

### custom.list.chrootの設定
config/package-listsの中に，custom.list.chrootファイルを作成する．

### 初めてisoを生成する場合
#!/bin/sh

set -e

lb config noauto \
--mirror-bootstrap "http://ftp.jp.debian.org/debian/" \
--mirror-chroot "http://ftp.jp.debian.org/debian/" \
--mirror-binary "http://ftp.jp.debian.org/debian/" \
-a amd64 \
--bootappend-live "boot=live components username=mpi locales=ja_JP.UTF-8 keyboard-layouts=ja utc=no timezone=Asia/Tokyo" \
--distribution bookworm \
--archive-areas "main contrib non-free non-free-firmware" \
"${@}"

lb config  
lb build

### 再度isoを生成する場合
lb clean  
lb config  
lb build  

## USBへisoイメージを書き込む
fdisk -l  
dd if=./live-image-amd64.hybrid.iso of=/dev/sdc bs=1048576
