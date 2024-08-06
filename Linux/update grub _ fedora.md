### edit
`/etc/default/grub`

### update 


On BIOS-based machines, issue the following command as root:

`sudo grub2-mkconfig -o /boot/grub2/grub.cfg`

On UEFI-based machines, issue the following command as root:

`sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg`

