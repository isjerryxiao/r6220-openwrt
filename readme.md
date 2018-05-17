# OpenWRT dist
[![Build Status](https://travis-ci.org/Jerry981028/r6220-openwrt.svg?branch=master)](https://travis-ci.org/Jerry981028/r6220-openwrt)  
Build with Travis Ci.  
This project is only for OpenWRT routers.
[You may want original project here.](http://openwrt-dist.sourceforge.net)

## Usage
You can use the following command to get architecture.  
`opkg print-architecture |awk '{print $2}' |tail -n 1`  
First, check your architecture before proceeding to the next steps. It should be `mipsel_24kc`.

Then, add the following line to `/etc/opkg.conf`. 
```
src/gz simonsmh_base https://github.com/Jerry981028/r6220-openwrt/raw/ramips/packages/mipsel_24kc/base
src/gz simonsmh_packages https://github.com/Jerry981028/r6220-openwrt/raw/ramips/targets/ramips/mt7621/packages
```

Now, you can install whatever you want.
```
opkg update
opkg install ChinaDNS
opkg install luci-app-chinadns
opkg install dns-forwarder
opkg install luci-app-dns-forwarder
opkg install shadowsocks-libev
opkg install luci-app-shadowsocks
opkg install pdnsd
opkg install luci-app-pdnsd
```
For more detail please check the `base` directory.  
You can also search and install them in LuCI or SCP/FTP upload these downloaded files to your router, then login to your router and use opkg to install these .ipk file.
## Build it yourself
[Check here](https://github.com/simonsmh/openwrt-dist/blob/master/.travis.yml)

## License
GPLv3

## Credit
Copyright © 2017 simonsmh
