# BulkSMS

# Installation of BulkSMS 
```
lxc launch images:debian/10 BulkSMS
```
```
lxc exec BulkSMS -- bash
```
```
vi /etc/apt/source.list
```
List of sourcelist
```
#

# deb cdrom:[Debian GNU/Linux 10.13.0 _Buster_ - Official amd64 DVD Binary-1 20220910-18:04]/ buster contrib main

#deb cdrom:[Debian GNU/Linux 10.13.0 _Buster_ - Official amd64 DVD Binary-1 20220910-18:04]/ buster contrib main

# Line commented out by installer because it failed to verify:
#deb http://security.debian.org/debian-security buster/updates main contrib
# Line commented out by installer because it failed to verify:
#deb-src http://security.debian.org/debian-security buster/updates main contrib

# buster-updates, previously known as 'volatile'
# A network mirror was not selected during install.  The following entries
# are provided as examples, but you should amend them as appropriate
# for your mirror of choice.
#
 deb http://deb.debian.org/debian/ buster main contrib
 deb-src http://deb.debian.org/debian/ buster main contrib
```
ctrl+x 
and yes
```
apt update
```
```
apt-get install nano wget
```
```
apt-get install libtool shtool automake dahdi-source libssl-dev sqlite3 libsqlite3-dev libsctp-dev libfftw3-dev libfftw3-3 autoconf libsctp-dev libgnutls28-dev libcurl4-gnutls-dev git-core pkg-config make gcc gcc-arm-none-eabi doxygen libtalloc-dev libpcsclite-dev libusb-1.0-0-dev
```
```
apt-get install build-essential gcc g++ make automake autoconf libtool pkg-config libtalloc-dev libpcsclite-dev libortp-dev libsctp-dev libssl-dev libdbi-dev libdbd-sqlite3 libsqlite3-dev libpcap-dev libc-ares-dev libgnutls28-dev libsctp-dev sqlite3 libsofia-sip-ua-glib-dev libusb-1.0-0-dev libfftw3-dev libgsm1-dev
```
```
apt-get install autoconf automake build-essential ccache cmake cpufrequtils doxygen ethtool g++ git inetutils-tools libboost-all-dev libncurses5 libncurses5-dev libusb-1.0-0 libusb-1.0-0-dev libusb-dev python3-dev python3-mako python3-numpy python3-requests python3-scipy python3-setuptools python3-ruamel.yaml
```
```
apt-get install libtool shtool automake dahdi-source libssl-dev sqlite3 libsqlite3-dev libsctp-dev libfftw3-dev libfftw3-3 autoconf libsctp-dev libgnutls28-dev libcurl4-gnutls-dev git-core pkg-config make doxygen libtalloc-dev libpcsclite-dev libusb-1.0-0-dev
```
```
apt-get install asterisk telnet python3-pip
```
```
pip3 install smpplib
```
Installing dependencies before libosmo-abis
```
apt-get install libortp-dev
```
```
apt-get install fuse zip
```
```
sudo apt-get install libfuse-dev 
```
Creating and installing all components
```
mkdir src
```


Installing UHD
```
cd src 
```
```
git clone --depth 1 -b v3.15.0.0 https://github.com/EttusResearch/uhd
```
```
cd uhd/host
```
```
mkdir build
```
```
cd build
```
```
cmake ..
```
```
make -j4
```
```
sudo make install
```
```
sudo ldconfig
```
```
cd ../../..
```


Installing libosmocore
```
git clone --depth 1 -b 1.0.1 https://gitea.osmocom.org/osmocom/libosmocore
```
```
cd libosmocore
```
```
autoreconf -fi
```
```
./configure
```
```
make -j4
```
```
make check
```
```
sudo make install
```
```
sudo ldconfig
```
```
cd ..
```
"# 51/51


Just for memos : 
git clone git://git.osmocom.org/osmocom-bb.git  
cd osmocom-bb/  
git checkout 4f677e6ba8434dab376495cd996d140548fa6e93  
cd src  
nano target/firmware/Makefile  
"#uncomment CFLAGS += -DCONFIG_TX_ENABLE in the file target/firmware/Makefile"  
#ctrl+o return ctrl+x  
tail -f target/firmware/Makefile  
make -j4 -e CROSS_TOOL_PREFIX=arm-none-eabi-  
cd ../..  


FOR CALYPSO  
Installing libosmo-dsp
```
git clone git://git.osmocom.org/libosmo-dsp.git
```
```
cd libosmo-dsp/
```
```
git checkout 551b9752bcd5d3d21bb2df0736b1801bda3d0d10
```
```
autoreconf -i
```
```
./configure
```
```
make -j4
```
```
make install
```
```
ldconfig -i
```
```
cd ..
```
Installing trx
```
git clone git://git.osmocom.org/osmocom-bb.git -b fixeria/trx trx
```
```
cd trx/src/
```
```
git checkout 620fe497efa492feff4550e336cc3f8167715936
```
"#uncomment CFLAGS += -DCONFIG_TX_ENABLE in the file target/firmware/Makefile"
#ctrl+o return ctrl+x

```

```














