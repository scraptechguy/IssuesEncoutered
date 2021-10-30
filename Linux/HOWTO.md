## Printer installation

+ Note: This ONLY works for a specific printer (aump2000), but similar process will work with whatever printer you have

```
apt-get install cups
apt-get install printer-driver-gutenprint
```
http://localhost:631

socket://195.113.29.126:9100

+ Do NOT use old aump2000.ppd, but the one from Gutenprint!


## Debian 11 bullseye installation

```
apt-get install firmware-iwlwifi
apt-get install pulseaudio alsa-utils
apt-get install network-manager network-manager-applet
vi /etc/network/interfaces
# comment out enp0s25
reboot
```

+ Note: Uses systemd, not init.d :-(




