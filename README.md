# Quartz64_backup
My Quartz64 backup data

Dietpi V8.22.3 - kernel 6.5.5
- linux headers
- 
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
 # wifi net error
	 service networking restart
	 ifdown --force wlan0
	 ifup --force wlan0
	 modprobe 8812au
	#
 
== 
