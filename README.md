# gentoo_qemu<br>
Create an image 30G (at least)
1. ```$qemu-img create -f qcow2 Gentoo-VM.img 30G```
2. Download iso gentoo e.g. https://gentoo-mirror.alexxy.name//releases/amd64/autobuilds/20230220T081656Z/install-amd64-minimal-20230220T081656Z.iso
To boot from "cd" :
3. ```$./start_Gentoo_VM.sh -boot d -cdrom install-amd64-minimal-20120621.iso```
4. Follow the handbook (for amd54) start from the partition. <br>
a. [partion documentation](https://wiki.gentoo.org/wiki/Handbook:AMD64/Installation/Disks)
b. 


