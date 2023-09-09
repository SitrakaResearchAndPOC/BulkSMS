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
Tape ctrl+x  
and :w + enter  
and :q + ente  

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
apt-get install libfuse-dev 
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
make install
```
```
ldconfig
```
```
cd ../../..
```


Installing libosmocore 1.7.0 or 1.0.1
```
apt-get install libmnl-dev
```

```
git clone --depth 1 -b 1.7.0 https://gitea.osmocom.org/osmocom/libosmocore
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
make install
```
```
ldconfig
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
```
nano target/firmware/Makefile
```
"#uncomment CFLAGS += -DCONFIG_TX_ENABLE in the file target/firmware/Makefile"
#ctrl+o return ctrl+x
```
tail -f target/firmware/Makefile
```
```
make -j4 HOST_layer23_CONFARGS=--enable-transceiver -e CROSS_TOOL_PREFIX=arm-none-eabi-
```
```
cd ../..
```


Installing libosmo-abis
```
git clone --depth 1 -b 0.6.0 https://gitea.osmocom.org/osmocom/libosmo-abis
```
```
cd libosmo-abis
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
make install
```
```
ldconfig
```
```
cd ..
```
"# 2/2

Installing libosmo-netif
```
git clone --depth 1 -b 0.4.0 https://gitea.osmocom.org/osmocom/libosmo-netif
```
```
cd libosmo-netif
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
make install
```
```
ldconfig
```
```
cd ..
```
"# 3/3


Installing libosmo-sccp
```
git clone --depth 1 -b 1.0.0 https://gitea.osmocom.org/osmocom/libosmo-sccp
```
```
cd libosmo-sccp
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
make install
```
```
ldconfig
```
```
cd ..
```
"# 5/5


Installing libasn1
```
git clone --depth 1 -b 0.9.31 https://gitea.osmocom.org/cellular-infrastructure/libasn1c
```
```
cd libasn1c
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
make install
```
```
ldconfig
```
```
cd ..
```
"#


Installing libsmpp34
```
git clone --depth 1 -b 1.13.0 https://gitea.osmocom.org/cellular-infrastructure/libsmpp34
```
```
cd libsmpp34
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
make install
```
```
ldconfig
```
```
cd ..
```
"#
```
git clone --depth 1 -b 0.4.0 https://gitea.osmocom.org/cellular-infrastructure/osmo-iuh
```
```
cd osmo-iuh
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
make install
```
```
ldconfig
```
```
cd ..
```
"# 3/3


Installing osmo-ggsn maybe 1.9.0 or 1.3.0
```
git clone --depth 1 -b 1.9.0 https://gitea.osmocom.org/cellular-infrastructure/osmo-ggsn
```
```
cd osmo-ggsn
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
make install
```
```
ldconfig
```
```
cd ..
```
"# 5/5  
Installing osmo-sip-connector 1.3.1 or 1.2.0
```
git clone --depth 1 -b 1.3.1 https://gitea.osmocom.org/cellular-infrastructure/osmo-sip-connector
```
```
cd osmo-sip-connector
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
make install
```
```
ldconfig
```
```
cd ..
```

"#  
Installing osmotrx  1.2.0 or 1.2.2 or 1.0.2 or 1.0.0 
```
git clone --depth 1 -b 1.2.0 https://gitea.osmocom.org/cellular-infrastructure/osmo-trx
```
```
cd osmo-trx
```
```
autoreconf -fi
```
```
./configure --with-uhd
```
```
make -j4
```
```
make check
```
```
make install
```
```
ldconfig
```
```
cd ..
```

"# 5/7

Installing osmobts 1.2.2 or 1.0.0
```
git clone --depth 1 -b 1.2.2 https://gitea.osmocom.org/cellular-infrastructure/osmo-bts
```
```
cd osmo-bts
```
```
autoreconf -fi
```
```
./configure --enable-trx
```
```
make -j4
```
```
make check
```
```
make install
```
```
ldconfig
```
```
cd ..
```
"#8/8


Installing osmo-pcu  0.6.0  or 1.2.0 or 1.1.0 
```
git clone --depth 1 -b 0.6.0 https://gitea.osmocom.org/cellular-infrastructure/osmo-pcu
```
```
cd osmo-pcu
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
make install
```
```
ldconfig
```
```
cd ..
```
"# 12/12
Installing opensc 1.4.1 or 1.3.0
```
git clone --depth 1 -b 1.4.1 https://gitea.osmocom.org/cellular-infrastructure/openbsc
```
```
cd openbsc/openbsc
```
```
autoreconf -fi
```
```
./configure --enable-mgcp-transcoding --enable-nat --enable-smpp --enable-osmo-bsc
```
```
make -j4
```
```
make check
```
```
make install
```
```
ldconfig
```
```
cd ../..
```
"# 15/15

Installing osmo-hlr 1.0.0
```
git clone --depth 1 -b 1.0.0 https://gitea.osmocom.org/cellular-infrastructure/osmo-hlr
```
```
cd osmo-hlr
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
make install
```
```
ldconfig
```
```
cd ..
```
"# 5/5
Installing sgsn 1.6.2 or 1.4.0
```
git clone --depth 1 -b 1.6.2 https://gitea.osmocom.org/cellular-infrastructure/osmo-sgsn
```
```
cd osmo-sgsn
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
make install
```
```
ldconfig
```
```
cd ..
```
```
exit
```

"# 8/8

# Command you need : 
```
dmesg | grep ttyUSB*
```

# ADDING DEVICES ON LXC
```
lxc config device add BulkSMS ttyUSB0 unix-char path=/dev/ttyUSB0
```

# REMOVING DEVICES ON LXC
```
lxc config device remove BulkSMS ttyUSB0 
```

# CONFIGURING SCRIPT
```
lxc exec BulkSMS -- bash
```
```
wget https://raw.githubusercontent.com/SitrakaResearchAndPOC/nitb-script-all/main/osmo-nitb-scripts-calypsobts-v3.zip
```
```
unzip osmo-nitb-scripts-calypsobts-v3.zip 
```
```
cd osmo-nitb-scripts-calypsobts
```
Tape `*#*#4636#*#*` and choose GSM only on your Android phone  
Installing network signal guru on your android phone  
And finding the arfcn that this one is connect  
Let's name this arfcn as 975  
Configure arfcn at service/osmotrx.lms as 975
```
nano services/osmo-trx-lms3.service 
```
Save the configuration using ctrl+x
mkdir /usr/src/CalypsoBTS/


touch /usr/src/CalypsoBTS/hlr.sqlite3

cd osmo-nitb-scripts-calypsobts

```
bash install_services.sh 
```
For avoiding lock database error 
```
fuser -k /usr/src/CalypsoBTS/hlr.sqlite3
```
```
cd ..
```
```
cp -rf src/trx/  /usr/src/CalypsoBTS/
```
```
cd /usr/src/CalypsoBTS/
```
```
cp trx/src/host/osmocon/osmocon ../CalypsoBTS/
```
```
cp -rf trx/src/target/firmware/board ../CalypsoBTS/
```
```
mv board/ firmwares
```
```
cp trx/src/host/layer23/src/transceiver/transceiver ../CalypsoBTS/
```
```
chmod +x osmocon
```
```
chmod +x transceiver	
```
```
nano /usr/src/CalypsoBTS/osmo-bts-trx-calypso.cfg
```
Change the config file as  : [osmo-bts-trx-calypso.cfg](https://raw.githubusercontent.com/SitrakaResearchAndPOC/nitb-script-all/main/osmo-bts-trx-calypso.cfg)
```
exit
```
## Plug usb ttl

```
lxc config device add BulkSMS ttyUSB0 unix-char path=/dev/ttyUSB0
```
```
lxc config set BulkSMS security.privileged=true
```

## Testing TRX CALYPSO
```
lxc exec BulkSMS -- bash
```
```
cd osmo-nitb-scripts-calypsobts
```
```
nano trx.sh
```
Don't use sudo terminal in trx.sh
Running transceiver
```
bash trx.sh
```
Click button power of motorola phone  

or on Terminal
```
lxc exec BulkSMS -- bash osmo-nitb-scripts-calypsobts/trx.sh
```
Click button power of motorola phone  

## Testing CALYPSO SpoofScript1
Tape ctrl+shift+T
```
lxc exec BulkSMS -- python3 osmo-nitb-scripts-calypsobts/main_spoof.py
```
ctrl+shift+T
```
lxc exec BulkSMS -- bash osmo-nitb-scripts-calypsobts/scripts_spoof1/finding_imsi_extenstion.sh
```
You could find imsi and extension  
let's see for example imsi as 646040222463674 and extension as 126
```
lxc exec BulkSMS -- bash osmo-nitb-scripts-calypsobts/scripts_spoof1/set_imsi_extension.sh 646040222463674 0341220590
```
Verify by if the association is correct
let's see for example imsi as 646040222463674 and extension as 0341220590
```
bash finding_imsi_extenstion.sh
```
Tape `*#*#4636#*#*` and choose GSM only on your Android phone  
Search GSM network (on your phone), associate with PLMN MCC 001 && MNC 01  
Tape `*#001#` for finding your phone number (extension with osmo-bts)   
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof1/sending_sms_spoof_byextension.py
```
Sending for all extensions in osmo-bts
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof1/sending_sms_broadcast.py 
```
log should be :  subscriber extension 0341220590 sms sender extension 0341220590 send ALERT Corona virus  

## Testing CALYPSO SpoofScript2
ctrl+shift+T
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof2/show_subscribers.py 
```
You could find imsi and extension
Create a virtual extension 0341220590 and send sms to existing extension eg : 164
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof2/sms_send_source_dest_msg.py 0341220590 164 "link gmail"
```
You could find imsi and extension
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof2/show_subscribers.py 
```
Creating many extensions for sending a scam sms repeat 3 times
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof2/sms_spam.py 164 3 "link gmail"
```
You could find imsi and extension
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof2/show_subscribers.py 
```
Sending a broadcast sms by using a virtual number as extension 165
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof2/sms_broadcast.py 165 "link gmail"
```
You could find imsi and extension
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts-calypsobts/scripts_spoof2/show_subscribers.py
```
## Testing TRX UHD (USRP)
```
wget https://raw.githubusercontent.com/SitrakaResearchAndPOC/fork_QCSuperLXD/main/lxd-device
```
```
chmod +x lxd-device
```
```
sudo cp lxd-device /usr/local/bin
```
```
lxd-device add BulkSMS usrp
```
```
lxc exec BulkSMS -- uhd_images_downloader
```
```
lxc exec BulkSMS --  uhd_usrp_probe 
```
```
lxc exec BulkSMS -- uhd_find_devices 
```
```
lxc exec BulkSMS -- bash
```
```
mkdir /var/lib/osmocom/
```
```
touch /var/lib/osmocom/hlr.sqlite3
```
```
mkdir /etc/osmocom
```
```
touch /etc/osmocom/osmo-trx-uhd.cfg
```
```
nano osmo-trx-uhd.cfg
```
Add config [osmo-trx-uhd.cfg](https://raw.githubusercontent.com/SitrakaResearchAndPOC/nitb-script-all/main/osmo-trx-uhd.cfg)
```
wget https://raw.githubusercontent.com/SitrakaResearchAndPOC/nitb-script-all/main/osmo-nitb-scripts-v3.zip
```
```
unzip osmo-nitb-scripts-v3.zip
```
```
cd osmo-nitb-scripts
```
```
bash install_services.sh 
```
```
lxc exec BulkSMS -- bash 
```
```
osmo-trx-uhd -C /etc/osmocom/osmo-trx-uhd.cfg
```
```
lxc exec BulkSMS -- python3 osmo-nitb-scripts/main_uhd.py
```
```
exit
```


## Testing USRP SpoofScript1
```
lxc exec BulkSMS -- bash osmo-nitb-scripts/scripts_spoof1/finding_imsi_extenstion.sh
```
You could find imsi and extension  
let's see for example imsi as 646040222463674 and extension as 126
```
lxc exec BulkSMS -- bash osmo-nitb-scripts/scripts_spoof1/set_imsi_extension.sh 646040222463674 0341220590
```
Verify by if the association is correct
let's see for example imsi as 646040222463674 and extension as 0341220590
```
lxc exec BulkSMS -- bash osmo-nitb-scripts/scripts_spoof1/finding_imsi_extenstion.sh
```
Tape `*#*#4636#*#*` and choose GSM only on your Android phone  
Search GSM network (on your phone), associate with PLMN MCC 001 && MNC 01  
Tape `*#001#` for finding your phone number (extension with osmo-bts)   
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof1/sending_sms_spoof_byextension.py
```
Sending for all extensions in osmo-bts
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof1/sending_sms_broadcast.py 
```
log should be :  subscriber extension 0341220590 sms sender extension 0341220590 send ALERT Corona virus  

## Testing USRP SpoofScript2
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof2/show_subscribers.py 
```
You could find imsi and extension
Create a virtual extension 0341220590 and send sms to existing extension eg : 164
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof2/sms_send_source_dest_msg.py 0341220590 164 "link gmail"
```
You could find imsi and extension
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof2/show_subscribers.py 
```
Creating many extensions for sending a scam sms repeat 3 times
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof2/sms_spam.py 164 3 "link gmail"
```
You could find imsi and extension
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof2/show_subscribers.py 
```
Sending a broadcast sms by using a virtual number as extension 165
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof2/sms_broadcast.py 165 "link gmail"
```
You could find imsi and extension
```
lxc exec BulkSMS -- python2 osmo-nitb-scripts/scripts_spoof2/show_subscribers.py
```
```
exit
```


## SAVING IMAGE :
```
lxc publish BulkSMS --alias BulkSMS -f
```
Instance published with fingerprint: 0fd7664a00694613964919796da5d797f179a32df134f8a2bc46ae20dee62d69
```
lxc export BulkSMS .
```
```
md5sum 0fd7664a00694613964919796da5d797f179a32df134f8a2bc46ae20dee62d69.tar.gz 
```
06d4ed59da765e7e02427c6f4dd92b98  0fd7664a00694613964919796da5d797f179a32df134f8a2bc46ae20dee62d69.tar.gz

```
chmod 777 0fd7664a00694613964919796da5d797f179a32df134f8a2bc46ae20dee62d69.tar.gz
```
















































 




























