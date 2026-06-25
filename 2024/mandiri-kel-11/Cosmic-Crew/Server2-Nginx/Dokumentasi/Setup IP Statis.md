# Setup IP Statis 

 Konfigurasi IP statis pada interface Ethernet menggunakan **systemd-networkd**.

## Edit File Konfigurasi

```
/etc/systemd/network/20-wired.network
```

## Isi Konfigurasi

```
[Match]
Type=ether
Kind=!*

[Link]
RequiredForOnline=routable

[Network]
Address=10.10.1.253/24
Gateaway=10.10.1.1
DNS=1.1.1.1 8.8.8.8
MulticastDNS=yes

[DHCPv4]
RouteMetric=100

[IPv6AcceptRA]
```

## Terapkan Konfigurasi

```
sudo systemctl restart systemd-networkd
sudo systemctl restart systemd-resolved
```
