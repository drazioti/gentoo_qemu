# gentoo_qemu<br>
Create an image 30G (at least)
1. ```$qemu-img create -f qcow2 Gentoo-VM.img 30G```
2. Download iso gentoo e.g. ```install-amd64-minimal-20230220T081656Z.iso```
To boot from **cd** :
3. ```$./start_Gentoo_VM.sh -boot d -cdrom install-amd64-minimal-20230220T081656Z.iso```
4. Follow the handbook (for amd64). <br>
*a.* start from the **partition** [partition documentation](https://wiki.gentoo.org/wiki/Handbook:AMD64/Installation/Disks) <br>
In partition tables you have to replace ```/dev/sdaX``` that you read from handbook with ```/dev/vdaX```. Continue with the filesystem
boot,swap,ext4.<br>
*b.* Continue with mounting /dev/vda3, fixing date, **download the stage3 tar**, e.g. ```stage3-amd64-desktop-openrc-...tar.xz```, set for instance ```MAKEOPTS="-j4" ``` in ```/etc/portage/make.conf```<br>
This step is important, since after mounting, you can close the virtual machine, and later remounting the partition, you can continue from tha last point<br>
*c.* Continue with mounting other basic systems to /mnt/gentoo, and then chrooting.
Again, this is important, you can close the vm, and after mounting+chrooting you can continue the set up.<br>
Select profile, set license and **installing the base system**<br>
After chrooting, ypu have to configure portage by ```$emerge-webresync```<br>
*d.* The next step is to **configure the kernel**. Choose a method, for instance genkernel. <br>
*e.* **Configure the system**. Be careful when you create ```fstab```, since when you reboot you may consider ```kernel panic```<br>
You have to set the hostname,network, set root password, set openshh, set a new user with wheel group, and add the group ```wheel``` to the sudoers file, e.g. ```$visudo```<br>
*f.* set the **bootloader** grub or lilo.<br>
*g.* **poweroff** (exit,unmount,poweroff).<br>
Now boot from the **drive** :<br>
 ```$./start_Gentoo_VM.sh```
