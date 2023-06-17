
# squid4 for autoinstall  with dns-crypt&unbound

# replace with your ip address on the config below :
* unbound.conf ---->  replace with the your IP address proxy and domain
* squid.conf ----> replace with your ip address proxy
* rc.local ----> replace with your ip address proxy

# repository by indonesia server

```
#installation
##########################################
start the installation with git clone
```bash
#installasi complete software 
apt-get install devscripts build-essential openssl libssl-dev fakeroot libcppunit-dev pkg-config libsasl2-dev cdbs ebtables bridge-utils libcap2 libcap-dev libcap2-dev sysv-rc-conf iproute kernel-package libncurses5-dev fakeroot wget bzip2 debhelper linuxdoc-tools libselinux1-dev htop iftop dnstop perl libnet-ssleay-perl openssl libauthen-pam-perl libpam-runtime libio-pty-perl apt-show-versions python ccze pastebinit checkinstall libssl-dev htop iftop iptraf mtr-tiny bwm-ng ccze sysv-rc-conf devscripts build-essential openssl libssl-dev fakeroot libcppunit-dev libsasl2-dev cdbs ccze libfile-readbackwards-perl libcap2 libcap-dev libcap2-dev libnetfilter-conntrack-dev libfile-readbackwards-perl -y
apt-get install git g++-4.4 -y
git clone https://github.com/githubazza/squid4-autoinstall.git
cd squid4-autoinstall
chmod +x squid4.sh
./squid4.sh
```

## after reboot 
```bash
delete dns-nameservers di /etc/network/interfaces or comment #dns-nameservers
/etc/init.d/networking restart
squid -k reconfigure
/etc/init.d/squid restart
/etc/init.d/unbound restart
dig google.com
unbound-control stats tail -16
tail -f /var/log/squid/access.log
```
