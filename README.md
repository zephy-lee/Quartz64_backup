# Quartz64_backup
My Quartz64 backup data

Dietpi v8.24 - kernel 6.5.11
- linux headers

Dietpi V8.22.3 - kernel 6.5.5
- linux headers

DietPi v8.16 - kernel 6.2.14
 - linux-headers
 - rtl8812au.ko-6.2.14

DietPi v8.12 - kernel 6.1.0-rc1
 - linux-headers
 - rtl8812au.ko-6.1.0-rc1

DietPi v8.x - kernel 5.19.0-rc1
 - linux-headers

== current server setting
- DietPi v8.12 + OMV 6.1
 - OMV service
   + MiniDLNA
   + Symlinks
   + docker - portainer, yacht
     + jellyfin
     + photoprism + mariadb
     + aria2-pro + ariang
     + transmission
     + haproxy
     
==      
 network error after boot - add postboot (restart network)
	#net
	service networking stop
 
	ifdown --force wlan0
	# ifup --force wlan0
	modprobe 88XXau
	#wpa_supplicant -B -i wlan0 -c /etc/wpa_supplicant/wpa_supplicant.conf
	#ifup --force wlan0
	/boot/dietpi/func/dietpi-set_hardware wifimodules enable
	ifup --force wlan0
	#/etc/init.d/networking force-reload
	service networking start
 
== 
