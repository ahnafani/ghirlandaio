# Setup Linux Hardened
```
sudo su
```
```
pacman -S linux-harderned linux-hardened-headers
```

## Menyesuaikan Preset Mkinitcpio
```
nvim /etc/mkinitcpio.d/linux-lts.preset
```
>Cek konfigurasi kernel lts, sebagai referensi sebelum mengonfigurasi kernel hardened

```
nvim /etc/mkinitcpio.d/linux-harderned.preset
```
```
mkinitcpio -P
```
```
ls /boot/efi/linux/linux-harderned-headers
```

## Menyesuaikan Konfigurasi Boot
```
nvim /etc/mk
```
```
nvim /etc/mkinitcpio.d/
```
```
nvim /etc/mkinitcpio.d/linux-hardened.preset
```
```
cat /etc/mkinitcpio.d/linux-lts.preset
```

## Menempatkan Kernel ke Direktori Boot
```
cd /boot/
```
```
ls
```
```
mv vmlinuz-linux-hardened kernel/
```
```
ls
```

## Verifikasi EFI Image
```
mkinitcpio -P
```
```
ls /boot/efi/linux/arch-linux-hardened.efi
```

## Selesai
```
exit
```


# Setup Firewall

## Masuk Sebagai Root
```
sudo su
```

## Cek status firewalld
Pastikan statusnya aktif dan enable
```
systemctl status firewalld
```

## Melihat List Zona
```
firewall-cmd --list-all-zone
```
## Menghapus Akses SSH Pada Zona Tertentu
```
firewall-cmd --zone=work --remove-service=ssh --permanent
firewall-cmd --reload
```

```
firewall-cmd --zone=operator --remove-service=ssh --permanent 
firewall-cmd --reload
```

```
firewall-cmd --zone=nm-shared --remove-service={dhcp,dns,ssh} --permanent
firewall-cmd --reload
```

```
firewall-cmd --zone=admin --remove-service=ssh --permanent
firewall-cmd --reload
```

>Semua services pada bagian zone dihapus. Pengecualian untuk zona public, sisakan ssh.
 
>Gunakan {} apabila ada lebih dari satu dibagian services untuk tiap zona.

# Hardening Module Kernel
```
lsmod | grep cramfs
lsmod | grep freevxfs
lsmod | grep jffs2
lsmod | grep hfs
lsmod | grep hfsplus
lsmod | grep squashfs
lsmod | grep udf
lsmod | grep usb-storage
lsmod | grep bluetooth
```

## Menonaktifkan Module Yang Tidak Diperlukan
```
nvim /etc/modprobe.d/01-custum.conf
```
ADD
```
install bluetooth /bin/false
blacklist bluetooth
install usb-storage /bin/false
blacklist usb-storage
```

```
mkinitcpio -P
```

## Selesai
```
exit
```
