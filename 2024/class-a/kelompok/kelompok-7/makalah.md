# INSTALASI DESKTOP XFCE BESERTA FITUR-FITURNYA
Tugas ini disusun untuk memenuhi tugas mata kuliah Perpustakaan dan Arsip Digital
## Dosen Pengampu:
Al Muhdil Karim, S.IP, M.Hum.
## Disusun Oleh Kelompok 7:
1. Iskandar (12402051030027)
2. Muhammad Tri Andhika Yustisia (12402051030040)
3. Riski Hidayat (12402051050117)
# Kata Pengantar
Puji dan Syukur kami panjatkan ke hadirat Allah SWT yang Maha Esa atas segala rahmat dan karunia-Nya sehingga kami dapat menyelesaikan makalah ini dengan baik. makalah ini kami berikan judul “INSTALASI DESKTOP XFCE BESERTA FITUR-FITURNYA”.

Makalah ini disusun untuk memenuhi tugas kelompok pada mata kuliah Perpustakaan dan Arsip Digital. Tidak lupa juga kami ucapkan terima kasih kepada Bapak Al Muhdil Karim, S.IP, M.Hum. selaku dosen pengampu mata kuliah dan teman-teman yang telah ikut serta memberikan dukungan dan bantuan dalam proses penyusunan makalah ini.

Kami menyadari bahwa makalah ini masih jauh dari kata sempurna. Oleh karena itu, kritik dan saran yang membangun sangat kami harapkan demi penyempurnaan makalah ini di masa mendatang. Semoga makalah yang kami buat ini bermanfaat bagi para pembaca serta dapat menambah wawasan tentang Perpustakaan dan Arsip Digital.

# Bab I
## Pendahaluan
Arch Linux adalah distribusi GNU/Linux serbaguna x86-64 yang dikembangkan secara independen dan cukup fleksibel untuk memenuhi berbagai kebutuhan. Pengembangan berfokus pada kesederhanaan, minimalisme, dan keanggunan kode. Arch diinstal sebagai sistem dasar minimal, yang dikonfigurasi oleh pengguna, di mana lingkungan ideal mereka sendiri dirakit dengan hanya menginstal apa yang dibutuhkan atau diinginkan untuk tujuan unik mereka. Utilitas konfigurasi GUI tidak disediakan secara resmi, dan sebagian besar konfigurasi sistem dilakukan dari shell dengan mengedit file teks sederhana. Arch berupaya untuk selalu mengikuti perkembangan terbaru, dan biasanya menawarkan versi stabil terbaru dari sebagian besar perangkat lunak. Arch Linux menggunakan pengelola paket Pacman miliknya sendiri, yang menggabungkan paket biner sederhana dengan sistem pembuatan paket yang mudah digunakan. Hal ini memungkinkan pengguna untuk dengan mudah mengelola dan menyesuaikan paket mulai dari perangkat lunak resmi Arch hingga paket pribadi pengguna sendiri hingga paket dari sumber pihak ketiga. Sistem repositori juga memungkinkan pengguna untuk dengan mudah membangun dan memelihara skrip pembuatan, paket, dan repositori kustom mereka sendiri, mendorong pertumbuhan dan kontribusi komunitas. Kumpulan paket dasar Arch minimal berada di repositori [core] yang disederhanakan. Selain itu, repositori resmi [extra], [extra-testing], dan [core-testing] menyediakan beberapa ribu paket berkualitas tinggi untuk memenuhi kebutuhan perangkat lunak Anda. Arch juga menawarkan Arch Linux User Repository (AUR), yang berisi lebih dari 49.000 skrip build, untuk mengkompilasi paket yang dapat diinstal dari kode sumber menggunakan aplikasi makepkg Arch Linux. Arch Linux menggunakan sistem "rilis bergulir" yang memungkinkan instalasi satu kali dan peningkatan perangkat lunak secara terus-menerus. Umumnya tidak perlu menginstal ulang atau meningkatkan sistem Arch Linux Anda dari satu "versi" ke versi berikutnya. Dengan menjalankan satu perintah, sistem Arch akan selalu mutakhir dan berada di garis terdepan. Arch berupaya menjaga agar paket-paketnya sedekat mungkin dengan perangkat lunak sumber aslinya. Patch hanya diterapkan jika diperlukan untuk memastikan aplikasi dapat dikompilasi dan dijalankan dengan benar bersama paket-paket lain yang terpasang pada sistem Arch yang mutakhir.

Konfigurasi sistem pada tabel tersebut menunjukkan rancangan lingkungan kerja berbasis Arch Linux yang dirancang dengan fokus pada keamanan, efisiensi, fleksibilitas, dan performa sistem. Sistem ini menggunakan Booster sebagai initramfs generator untuk mempercepat proses booting, serta menerapkan metode enkripsi “LUKS on LVM” guna memberikan perlindungan data sekaligus fleksibilitas pengelolaan partisi. Antarmuka desktop menggunakan XFCE karena ringan dan stabil, sedangkan Superfile dipilih sebagai file manager berbasis terminal yang modern dan efisien. Layout disk mengikuti standar CIS (Center for Internet Security) yang menekankan pemisahan partisi penting demi meningkatkan keamanan sistem. Untuk kebutuhan containerisasi digunakan Podman dan Podman Desktop karena mendukung rootless container yang lebih aman dibanding pendekatan tradisional. Sistem keamanan jaringan diperkuat menggunakan iptables sebagai firewall untuk mengatur lalu lintas jaringan masuk dan keluar. Pada sisi multimedia digunakan MPD, MPC, dan MPV yang dikenal ringan dan optimal untuk lingkungan Linux minimalis. Pengelolaan password dilakukan menggunakan KeePassXC yang menyediakan penyimpanan password terenkripsi, sedangkan OpenSSH digunakan untuk akses jarak jauh secara aman melalui protokol SSH. Keseluruhan konfigurasi ini menunjukkan implementasi sistem Linux modern yang tidak hanya berorientasi pada penggunaan sehari-hari, tetapi juga memperhatikan aspek keamanan data, efisiensi resource, stabilitas sistem, dan kemudahan administrasi.

## Rumusan Masalah
- Bagaimana langkah instalasi booster
- Bagaimana langkah disk enkripsi luks on lvm
- Bagaimana langkah menginstall dekstop xfce
- Bagaimana langkah menginstall super file
- Bagaimana langkah disk layout CIS
- Bagaimana langkah instalasi podman, podman desktop
- Bagaimana langkah instalasi Firewall iptables
- Bagaimana langkah instalasi mpd,mpc,mpv
- Bagaimana langkah instalasi password keepass xc
- Bagaimana langkah instalasi key secret
- Bagaimana langkah acces openssh

## Tujuan Masalah
- Menjelaskan langkah instalasi booster
- Menjelaskan langkah mengdisk enkripsi luks on lvm
- Menjelaskan langkah menginstall desktop xfce
- MEnjelaskan langkah menginstall super file
- Menjelaskan langkah mengdisk layout CIS
- Menjelaskan langkah instalasi pdman, podman desktop
- Menjelaskan langkah instalasi Firewall iptables
- Menjelaskan langkah instalasi mpd, mpc, mpv
- Menjelaskan langkah instalasi password keepass xc
- Menjelaskan langkah instalasi key secret
- Menjelaskan langkah penggunaan acces openssh

# Bab II
## Pembahasan
