# gentoo_qemu<br>
Create an image 30G (at least)
1. ```$qemu-img create -f qcow2 Gentoo-VM.img 30G```
2. Download iso gentoo e.g. https://gentoo-mirror.alexxy.name//releases/amd64/autobuilds/20230220T081656Z/install-amd64-minimal-20230220T081656Z.iso
To boot from "cd" :
3. ```$./start_Gentoo_VM.sh -boot d -cdrom install-amd64-minimal-20120621.iso```
4. Follow the handbook (for amd64). <br>
*a.* start from the **partition** [partion documentation](https://wiki.gentoo.org/wiki/Handbook:AMD64/Installation/Disks) <br>
In partition tables you have to replace ```/dev/sdaX``` that you read from handbook with ```/dev/vdaX```. Continued with the filesystem
boot,swap,ext4.<br>
*b.* Continue with fixing date, **download the stage tar**, set ```MAKEOPTS="-j4" ``` in ```/etc/portage/make.conf```<br>
*c.* Conitnue with mounting,chrooting, select profile, set license and **installing the base system**<br>
*d.* 

