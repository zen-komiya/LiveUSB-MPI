# LiveUSB-MPI


### 初めてisoを生成する場合
lb config  
lb build

### 再度isoを生成する場合
lb clean  
lb config  
lb build  

## USBへisoイメージを書き込む
fdisk -l  
dd if=./live-image-amd64.hybrid.iso of=/dev/sdc bs=1048576
