# Dokumentasi Penginstalan Linux lts
## Nama: Fatma Ramadhani
## NIM: 12402051050157
## Mata Kuliah: Perpustakaan dan Arsip Digital
## Dosen Pengampu: Al Muhdil Karim, S. IP., M.Hum
# Tahap Persiapan
## 1. Instalasi Linux lts Blackbird Amanda
Cek wifi
```bash
iwctl
```
---
```bash
device list
```
---
```bash
station wlan0 connect "nama wifi"
```
```
exit
```
## 2. Verifikasi koneksi internet
```bash
ping detik.com
```
## 3. Membuat Filesystem Ext4
```bash
lsblk
```
```bash
mkfs.ext4 -b 4096 /dev/(nama grup)/root
mkfs.ext4 -b 4096 /dev/(nama grup)/vars
mkfs.ext4 -b 4096 /dev/(nama grup)/vtmp
mkfs.ext4 -b 4096 /dev/(nama grup)/vlog
mkfs.ext4 -b 4096 /dev/(nama grup)/vaud
mkfs.ext4 -b 4096 /dev/(nama grup)/home
mkfs.ext4 -b 4096 /dev/(nama grup)/dock
mkfs.vfat -F32 -n BOOT /dev/(nama boot efi system)
```
---
```bash
lsblk
```
## Mounting
partisi root
```bash
mount /dev/proc/root /mnt
```
partisi vars
```bash
mount --mkdir -o rw,nodev,nosuid,relatime /dev/(nama grup)/vars /mnt/var
```
partisi vtmp
```bash
mount --mkdir -o rw,nodev,nosuid,noexec,relatime /dev/(nama grup)/vtmp /mnt/var/tmp
```
partisi vlog
```bash
mount --mkdir -o rw,nodev,nosuid,noexec,relatime /dev/(nama grup)/vlog /mnt/var/vlog
```
partisi vaud
```bash
mount --mkdir -o rw,nodev,nosuid,noexec,relatime /dev/(nama grup)/vaud /mnt/var/log/audit
```
partisi home
```bash
mount --mkdir -o rw,nodev,nosuid,relatime /dev/(nama grup)/home /mnt/home
```
partisi dock
```bash
mount --mkdir -o rw,nodev,nosuid,relatime /dev/(nama grup)/dock /mnt/var/lib/docker
```
