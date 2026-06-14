# masuk mode root

sudo su

masukan password root

#  nvim /etc/iwd/main.conf 
lalu masukan command berikut:
                                                                                                                                              
[General]                                                                                                                                           
EnableNetworkConfiguration=true   

setelah itu write dan quit menggunakan :wq

# nvim /etc/modprobe.d/hardening.conf     
lalu masukan command berikut:

install         cramfs          /bin/false                                                                                                          
install         freexfs         /bin/false                                                                                                          
install         hfs             /bin/false                                                                                                       
install         hfsplus         /bin/false                                                                                                          
install         jffs2           /bin/false                                                                                                          
install         udf             /bin/false                                                                                                          
install         fire-wire-core  /bin/false                                                                                                          
install         usb_storage     /bin/false       

lalu write dan quit menggunakan :wq

# mkinitcpio -P

untuk membuat ulang konfigurasi yang baru dirubah

# lsmod

untuk melihat list module kernel yang ada

# systemctl status firewalld

untuk melihat apakah firewalld sudah berfungsi atau belum, kalau belum bisa enable dan start menggunakan command

# systemctl enable firewalld
# systemctl start firewalld

lalu masukan command 

firewall-cmd --zone=public --add-port=8080/tcp --permanent 

firewall-cmd --zone=public --add-port=3306/tcp --permanent 

firewall-cmd --zone=public --add-port=2377/tcp --permanent

firewall-cmd --zone=public --add-port=7946/tcp --permanent  

firewall-cmd --zone=public --add-port=7946/udp --permanent    

irewall-cmd --zone=public --add-port=4789/udp --permanent   

firewall-cmd --reload  


# firewall-cmd --list-all  
untuk cek port yang sudah di konfigurasi
