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

dd if=./linuxmint-18.1-cinnamon-64bit.iso of=/dev/sdd bs=1048576
