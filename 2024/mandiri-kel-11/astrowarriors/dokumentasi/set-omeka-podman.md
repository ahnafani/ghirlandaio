# Set Omeka Podman

```
sudo systemctl enable --global podman
```

```
systemctl status podman
```

```
sudo su
```

buat direktori
```
mkdir [terserah]
```

```
cd [terserah]/
```

buat direktori omeka
```
mkdir omeka
```

```
cd omeka/
```

buat direktori config
```
mkdir config
```

buat direktori files
```
mkdir files
```

buat hak akses direktori
```
chmod 777 config/
chmod 777 files/
```

```
ls -la
```

```
cd config/
```

buat file
```
nvim database.ini
```
isi
```
.
```

```
cd ..
```

buat file
```
nvim docker-compose.yml
```
isi
```
.
```

pull image
```
podman compose up -d
```
