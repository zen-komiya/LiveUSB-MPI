# LiveUSB-MPI

### custom.list.chrootの設定
config/package-listsの中に，custom.list.chrootファイルを作成する．

### 初めてisoを生成する場合
lb config --mirror-bootstrap "http://ftp.jp.debian.org/debian/"  
lb config --mirror-chroot "http://ftp.jp.debian.org/debian/"  
lb config --mirror-binary "http://ftp.jp.debian.org/debian/"  
lb config -a amd64  
lb config --bootappend-live "boot=live components locales=ja_JP.UTF-8 keyboard-layouts=ja"  
lb config --distribution bookworm  
lb config --archive-areas "main contrib non-free non-free-firmware"   

bullseyeという記述がconfig内のそこかしこにあるので，bookwormに書き換える．これが正しいやり方かは不明  

lb config  
lb build

### 再度isoを生成する場合
lb clean  
lb config  
lb build  

## USBへisoイメージを書き込む
fdisk -l  
dd if=./live-image-amd64.hybrid.iso of=/dev/sdc bs=1048576
