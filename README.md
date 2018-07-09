## Netfilter and iptables extension for [FULLCONENAT](https://github.com/Chion82/netfilter-full-cone-nat) target ported to OpenWrt.

Compile
---
```
# cd to OpenWrt source path
# Clone this repo
git clone -b master --single-branch https://github.com/LGA1150/openwrt-fullconenat package/fullconenat
# Select Network -> Firewall -> iptables-mod-fullconenat
make menuconfig
# Compile
make V=s
```

Usage
---
You can apply [this patch](https://github.com/LGA1150/fullconenat-fw3-patch) to OpenWrt's Firewall3 (Recommended).

Or manually add the following rules to `/etc/firewall.user`
```
iptables -t nat -A zone_wan_prerouting -j FULLCONENAT
iptables -t nat -A zone_wan_postrouting -j FULLCONENAT
```
