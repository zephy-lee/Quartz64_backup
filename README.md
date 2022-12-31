# Quartz64_backup
My Quartz64 backup data

DietPi v8.12 - kernel 6.1.0-rc1
 - linux-headers
 - rtl8812au.ko

DietPi v8.x - kernel 5.19.0-rc1
 - linux-headers



== install step
1. install - Dietpi 
 a. image burn using Etcher(balenaEtcher-xx)
 b. device setup
  - ssh -> openssh , log off, others off, service스 unmask, (time sync ?)
(check - omv comp. ref > https://dietpi.com/forum/t/manual-openmediavault-install/4089/2)

2. install - omv (https://docs.openmediavault.org/en/stable/installation/on_debian.html)
 a. Apt source list update
 
 cat <<EOF >> /etc/apt/sources.list.d/openmediavault.list
 deb http://packages.openmediavault.org/public shaitan main 
 '# deb http://downloads.sourceforge.net/project/openmediavault/packages shaitan main 
 '## Uncomment the following line to add software from the proposed repository.
 '# deb http://packages.openmediavault.org/public shaitan-proposed main
 '# deb http://downloads.sourceforge.net/project/openmediavault/packages shaitan-proposed main
 '## This software is not part of OpenMediaVault, but is offered by third-party
 '## developers as a service to OpenMediaVault users.
 '# deb http://packages.openmediavault.org/public shaitan partner
 '# deb http://downloads.sourceforge.net/project/openmediavault/packages shaitan partner
 EOF
 
 b. install cmd

 export LANG=C.UTF-8
 export DEBIAN_FRONTEND=noninteractive
 export APT_LISTCHANGES_FRONTEND=none
 apt-get install --yes gnupg
 wget -O "/etc/apt/trusted.gpg.d/openmediavault-archive-keyring.asc" https://packages.openmediavault.org/public/archive.key
 apt-key add "/etc/apt/trusted.gpg.d/openmediavault-archive-keyring.asc"
 apt-get update
 apt-get --yes --auto-remove --show-upgraded \
    --allow-downgrades --allow-change-held-packages \
    --no-install-recommends \
    --option DPkg::Options::="--force-confdef" \
    --option DPkg::Options::="--force-confold" \
 install openmediavault-keyring openmediavault
 
 c. install extra
   - wget -O - https://github.com/OpenMediaVault-Plugin-Developers/packages/raw/master/install | bash
   - docker install -> portainer, ...
 
3. setup serivces
 a. jellyfin
 b. photoprism
 c. miniDLNI, Symlinks

4. linux kernel
  https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git/refs/tags?h=v6.1.1
