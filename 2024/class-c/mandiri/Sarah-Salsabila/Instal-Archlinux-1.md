# **Instalasi Archlinux dan KDE Plasma** #

### Apa itu Linux (Arch Linux)? ###

Linux adalah sistem operasi yang bersifat open source, dan fokus utamanya adalah **Arch Linux**. Arch linux dikenal sebagai distribusi yang mengikuti model *rolling release*,
yang berarti setelah diinstal tidak perlu lagi mengisntal ulang untuk mendapatkan versi terbaru, cukup lakukan pembaruan sistem secara berkala.

### Apa itu KDE Plasma? ###

KDE Plasma adalah sebuah Desktop Environment (DE) atau lingkungan desktop grafis yang berjalan di atas sistem oprasi linux. Fungsinya adalah mengubah tampilan baris 
perintah CLI (*Command Line Interface*) yang berbasis teks menjadi antarmuka visual yang modern dan interaktif.

# **Persiapan Sebelum Instalasi** #
Persiapan yang perlu dilakukan sebelum menginstal Arch Linux dan KDE Plasma adalah sebagai berikut :

1. Pastikan *Device Encryption* itu OFF, hal ini dilakukan untuk *Dual-Boot* (Menjalankan windows dan Archlinux secara berdampingan)
   <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 21 38" src="https://github.com/user-attachments/assets/120d192a-4d85-44c9-af62-1cea6c41f911" />

2. Mengunduh file ISO Archlinux dari situs resmi, buka situs situs https://archlinux.org/download/  , lalu scroll ke bawah hingga menemukan bagian Indonesia dan pilih citrahost.com sebagai mirror unduhan.
   <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 29 36 (1)" src="https://github.com/user-attachments/assets/84a93647-6819-4ae5-a0fb-20ad1111c1c4" />
   <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 29 36" src="https://github.com/user-attachments/assets/41611ef2-05b3-4fd4-90ad-555f6c5d845a" />

   Kemudian setelah itu klik pada bagian **archlinux-2026.05.01-x86_64.iso**
   <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 29 37 (1)" src="https://github.com/user-attachments/assets/2d577149-5c12-41bb-b16b-e3bbacbfc0a8" />

3. Siapkan Flashdisk lalu unduh Rufus, Rufus berguna untuk membuat USB flashdisk biasa menjadi bootable media installer, yang berfungsi untuk menginstal sistem operasi baru (seperti Arch Linux atau Windows) ke komputer.
      lalu pilih yang bagian **rufus-4.14.exe**, tetapi sesuaikan kembali dengan PC atau Laptop yang sedang digunakan.
   <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 21 37" src="https://github.com/user-attachments/assets/e2c7b29d-04e6-439e-9e8b-81beacad19da" />


## Proses Instalasi ##

Setelah persiapan instalasi selesai, dilanjutkan dengan mengecek indikator visual harddisk atau SSD laptop/PC tersebut, guna memastikan skema partisi GPT (GUID Partition Table).
- Pertama-tama buka CMD (klik windows+r) kemudian akan muncul tampilan halaman CMD
  <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 21 38 (2)" src="https://github.com/user-attachments/assets/2837415a-40e0-486b-a31b-4b2fa2683dd7" />

  setelah itu ketik di CMD **diskpart** lalu setelah itu ketik lagi **listdisk**
  <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 21 40" src="https://github.com/user-attachments/assets/564aa146-708d-4609-8e44-b345ebfd9590" />

  setelah memastikan indikator visual harddisk atau SSD laptop/PC dengan format GPT, maka di lanjutkan dengan menentukan pengaturan di Rufus.

- Sebelum itu, sambungkan Laptop/PC dengan USB flashdisk lalu copypaste file ISO Archlinux yang telah di download kedalam USB flashdisk, kemudian masuk ke file Rufus yang telah kita instal, lalu ubah
  pengaturan pada **Boot Selection** pilih file Archlinux yang telah di copypaste (archlinux-2026.05.01-x86_64.iso).

- Lalu ubah pada bagian **Partition Scheme** menjadi GPT.
  <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 21 41 (1)" src="https://github.com/user-attachments/assets/2537b0b1-3e68-4899-9d23-f64d1a544619" />

- Kemudian buka Disk Management kemudian pilih yang windows lalu klik kanan dan pilih **Shrink**, fungsi shrink memotong ruang kosong yang tidak terpakai pada suatu partisi untuk menciptakan ruang
  penyimpanan baru tanpa menghapus data yang sudah ada.
  <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 29 37 (3)" src="https://github.com/user-attachments/assets/68607eaa-a4b9-4d60-b2d6-d0aa418fed7c" />

  kemudian atur sizenya sesuai keinginan kalian masing-masing, lalu klik shirk
  <img width="1600" height="900" alt="WhatsApp Image 2026-05-23 at 14 29 37 (2)" src="https://github.com/user-attachments/assets/7fbedfd6-67ae-40b6-a083-41b747339282" />

  
- Setelah itu masuk ke menu BIOS, cari tahu cara untuk booting jenis laptop yang digunakan. Lalu setelah itu akan muncul tampilan menu BIOS.
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 28" src="https://github.com/user-attachments/assets/a6474160-ccff-4b29-af94-db61cf51b2e1" />

- Lalu ke bagian SECURITY pilih **Secure Boot**  ubah menjadi **Disabled**
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 28 (1)" src="https://github.com/user-attachments/assets/4fea8bc4-7f1a-4edc-ac3e-b5b544468fe3" />

- Kemudian ke bagian **BOOT** ubah EFI USB DEVICE SanDisk (Partisi LInux) menjadi di paling atas
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 28 (2)" src="https://github.com/user-attachments/assets/1444f321-2f6f-4a24-9e40-af5354aeb47a" />

  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 29" src="https://github.com/user-attachments/assets/ceb38882-dfc2-458f-99dc-72c76d149750" />

- Setelah itu **Save and Exit** lalu pilih **Yes**
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 29 (1)" src="https://github.com/user-attachments/assets/856a0104-516a-4ffe-b6ec-a75b25758e84" />

  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 29 (2)" src="https://github.com/user-attachments/assets/268b5658-ede3-47f9-a30f-f1f4b68640ed" />

 - Kemudian layar laptop akan mati tunggu sampai muncul bacaan
    <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 57 (1)" src="https://github.com/user-attachments/assets/c546da8c-fb9d-4128-ad4e-daf7e31e2ae6" />

   Maka setelah itu akan masuk ke halaman pengaturan coding Archlinux
    <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 30" src="https://github.com/user-attachments/assets/a652e3fa-6ccf-4d0d-a529-b1db34b1ec7a" />

- Dilanjutkan dengan mengetikan cat /sys/firmware/efi/fw_platform_size lalu klik enter, ini untuk mengecek apakah perangkat sudah siap.
    <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 36" src="https://github.com/user-attachments/assets/5e3e435a-3fc2-4828-b362-a9cc515b22d1" />

- Kemudian akan muncul angka 64 yang berarti tipe perangkat yang kita gunakan firmware UEFI versi 64-bit.

- Lalu untuk perintah menyambungkan laptop dengan jaringan internet/Wifi maka ketik **iwctl**, maka akan muncul tulisan berikut
    <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 49 57" src="https://github.com/user-attachments/assets/c4021d25-181d-43db-bcaa-c586704bdd7a" />

- Setelah itu untuk mengecek perangkat wireless/wifi ketik **device list**, maka akan muncul tulisan pemberitahuannya bahwa telah On.
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 15 54 55" src="https://github.com/user-attachments/assets/dd923350-b713-44ae-8377-067c7f46524c" />

  
- Lalu ketik **station wlan0 get-networks** lalu klik enter, maka akan muncul jaringan yang ada. Tetapi jika ingin mengetahui jaringan wifi apa saja yang terdapat di lingkungan
  tersebut bisa mengetikkan **station wlan0 scan** lalu klik enter. Kemudian di lanjutkan untuk menyambungkan wifi/jaringan yang ingin kita gunakan bisa
  mengetikkan **station waln0 connet (masukan nama wifi/jaringan yang ingin digunakan)**. Lalu masukkan password wifi/jaringan.
  Perlu di perhatikan apakah kita sudah tersambung dengan wifi/jaringan yang kita inginkan maka di dekat nama jaringan/wifi akan muncul tanda **>**.
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 16 34 15" src="https://github.com/user-attachments/assets/d32dc21a-f296-414a-8638-b6b26d36416b" />

- Selanjutnya untuk mengecek apakah sudah benar-benar tersambung dengan jaringan/wifi ketik **exit** lalu klik enter. Setelah itu ketik **ping google.com** jika muncul tulisan yang banyak
  berarti sudah benar-benar tersambung dengan jaringan/wifi, kemudian jika sudah tersambung untuk menghentikannya pencet tombol (ctrl+C) maka akan otomatis tulisan tersebut berhenti.
  <img width="1280" height="437" alt="WhatsApp Image 2026-05-23 at 16 37 26" src="https://github.com/user-attachments/assets/1724bf4e-8b67-4ed8-8238-d6e3f20164dd" />

- Untuk mengecek partisi di linux maka ketikkan **lsblk -o name,fstype,size** lalu klik enter.
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 16 48 18" src="https://github.com/user-attachments/assets/78522514-90a0-48a8-b6c9-fb0805af3ef6" />

- Selanjutnya ketik **cfdisk /dev/nvme0n1(ini adalah nama disk yang di gunakan oleh windows) untuk mengelola partisi. Perlu diketahui bahwa untuk setiap nama disk di berbagai
- laptop itu akan berbeda-beda.
  <img width="1280" height="635" alt="WhatsApp Image 2026-05-23 at 16 58 06" src="https://github.com/user-attachments/assets/a52b88e8-708d-403d-bbaf-004ff5a2efba" />


- Lalu pilih **Free space** kemudian pilih opsi **New** lalu tuliskan pada ukuran **partition size: 1G**. Selanjutnya arahkan lagi pada tulisan **free Space** lalu pilih opsi **Type**,
  pada **partition type** pilihlah **EFI System**, ini berguna untuk **Boot**(menyimpan semua file bootingan).
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 17 14 11" src="https://github.com/user-attachments/assets/17a104b7-40e9-4e44-b2a4-ddd1b25a992c" />

  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 17 25 47 (1)" src="https://github.com/user-attachments/assets/008073ed-a3bc-41f2-9976-6a4f93c6a3b0" />

  <img width="720" height="1280" alt="WhatsApp Image 2026-05-23 at 17 25 47" src="https://github.com/user-attachments/assets/2bef1b8c-6fda-4ded-94f8-0a7e1ac8e407" />


- Selanjutnya lakukan hal yang sama yaitu Lalu pilih **Free space** kemudian pilih opsi **New** lalu tuliskan pada ukuran **partition size: 4G**.
  Selanjutnya arahkan lagi pada tulisan **free Space** lalu pilih opsi **Type**, pilihlah **Linux swap**, ini berguna untuk **Swap** (ketika Ram penuh, semua datanya akan masuk kesini).
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 17 34 42" src="https://github.com/user-attachments/assets/46ba9575-dcf7-4fb0-be20-de70cfe31c5f" />

  <img width="720" height="1280" alt="WhatsApp Image 2026-05-23 at 17 34 42 (1)" src="https://github.com/user-attachments/assets/52dc0026-c43b-4cde-ba34-1d8ca3f5af52" />


- Untuk berikutnya pilih **free space** dengan **size 24.3G Linux filesystem** , lalu pilih opsi **Write** , lalu ketik **Yes** kemudian pilih opsi **Quit**.
  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 17 44 10" src="https://github.com/user-attachments/assets/28c409e0-c3c5-4a2a-9a2f-11be983ed613" />

  <img width="1280" height="576" alt="WhatsApp Image 2026-05-23 at 17 44 11" src="https://github.com/user-attachments/assets/a5540d23-a14f-4927-a9fc-21350ab9bdf4" />

  <img width="1280" height="720" alt="WhatsApp Image 2026-05-23 at 17 44 10 (1)" src="https://github.com/user-attachments/assets/833fb117-2d0c-494a-b381-10ec23ee55ce" />

  <img width="1280" height="576" alt="WhatsApp Image 2026-05-23 at 17 44 10 (2)" src="https://github.com/user-attachments/assets/1b69b1c0-251e-4756-abb9-65851c1cd199" />

- Selanjutnya ketik **lsblk -o name,fstype,size**
  <img width="1280" height="576" alt="WhatsApp Image 2026-05-23 at 17 48 15" src="https://github.com/user-attachments/assets/743528cd-9d7a-4c76-b39c-f692af4407ca" />

 **nvme0n1p5, nvme0n1p6, nvme0n1p7 merupakan partisi milik linux**

 
- Selanjutnya Ketik **mkfs.ext4 /dev/nvme0n1p7**(karena ini partisi Root).
  <img width="1280" height="576" alt="WhatsApp Image 2026-05-23 at 17 58 31" src="https://github.com/user-attachments/assets/00fc25e2-67d5-4629-8c19-289fbc5abf54" />


- Selanjutnya Ketik **mkfs.fat -F 32 /dev/nvme0n1p5**(karena ini partisi bootingnya).
  <img width="1600" height="720" alt="WhatsApp Image 2026-05-23 at 18 08 40" src="https://github.com/user-attachments/assets/81f6fa60-9db3-493f-abee-2b7b37cda3f6" />


- Selanjutnya Ketik **mkswap /dev/nvme0n1p6**(karena ini partisi swapnya) lalu klik enter. lalu setelah itu ketik **swapon /dev/nvme01p6**
  <img width="1600" height="358" alt="WhatsApp Image 2026-05-23 at 18 08 41" src="https://github.com/user-attachments/assets/df28e294-2566-438b-836f-1cc7b1439585" />


- Dilanjut ketik **lsblk -o name,fstype,size**
  <img width="1600" height="720" alt="WhatsApp Image 2026-05-23 at 18 08 41 (1)" src="https://github.com/user-attachments/assets/a7d16eea-60ca-4dc0-9c04-d5f8903a82b8" />

  dari situ terlihat partisi-partisi linux yang telah di buat


  








  

  

  

  

  


    












   


   




