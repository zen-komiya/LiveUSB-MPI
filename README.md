# LiveUSB-MPI

## USBへisoイメージを書き込む
fdisk -l
dd if=./linuxmint-18.1-cinnamon-64bit.iso of=/dev/sdd bs=1048576
