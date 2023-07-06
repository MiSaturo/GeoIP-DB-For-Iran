# Geo IP DB for Iran

# Introduction

This project automatically generates GeoIP files every Thursday, and provides a command line interface (CLI) for users to customize GeoIP files, including but not limited to V2Ray dat format routing rule file `geoip.dat` and MaxMind mmdb format file `Country.mmdb` .

This project releases GeoIP files automatically every Thursday. It also provides a command line interface(CLI) for users to customize their own GeoIP files, included but not limited to V2Ray dat format file `geoip.dat` and MaxMind mmdb format file `Country.mmdb`.

## The difference from the official version of GeoIP

- Mainland China IPv4 address data is integrated with [IPIP.net](https://github.com/17mon/china_ip_list/blob/master/china_ip_list.txt) and [@gaoyifan/china-operator-ip](https:// github.com/gaoyifan/china-operator-ip/blob/ip-lists/china.txt)
- Mainland China IPv6 address data combined with MaxMind GeoLite2 and [@gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip/blob/ip-lists/china6.txt)
- New category (convenient for users with special needs):
   - `geoip:cloudflare` (`GEOIP,CLOUDFLARE`)
   - `geoip:cloudfront` (`GEOIP,CLOUDFRONT`)
   - `geoip:facebook` (`GEOIP,FACEBOOK`)
   - `geoip:fastly` (`GEOIP,FASTLY`)
   - `geoip:google` (`GEOIP,GOOGLE`)
   - `geoip:netflix` (`GEOIP,NETFLIX`)
   - `geoip:telegram` (`GEOIP,TELEGRAM`)
   - `geoip:twitter` (`GEOIP,TWITTER`)

## Reference configuration

Use the reference configuration of this project's `.dat` format file in [V2Ray](https://github.com/v2fly/v2ray-core):

```json
"routing": {
   "rules": [
     {
       "type": "field",
       "outboundTag": "Direct",
       "ip": [
         "geoip:cn",
         "geoip:private",
         "ext:cn.dat:cn",
         "ext:private.dat:private",
         "ext:geoip-only-cn-private.dat:cn",
         "ext:geoip-only-cn-private.dat:private"
       ]
     },
     {
       "type": "field",
       "outboundTag": "Proxy",
       "ip": [
         "geoip:us",
         "geoip:jp",
         "geoip:facebook",
         "geoip:telegram",
         "ext:geoip-asn.dat:facebook",
         "ext:geoip-asn.dat:telegram"
       ]
     }
   ]
}
```

Use the reference configuration of this project's `.mmdb` format file in [Clash](https://github.com/Dreamacro/clash):

```yaml
rules:
   - GEOIP,PRIVATE,DIRECT,no-resolve
   - GEOIP,FACEBOOK,DIRECT
   - GEOIP,IR,DIRECT
```

Use the reference configuration of this project's `.mmdb` format file in [Leaf](https://github.com/eycorsican/leaf), see [Official README](https://github.com/eycorsican/leaf/blob /master/README.zh.md#geoip).

## download link

> If the domain `raw.githubusercontent.com` cannot be accessed, the second address `cdn.jsdelivr.net` can be used.
> *.sha256sum is the verification file.

### V2Ray dat format routing rule file

> Available for [V2Ray](https://github.com/v2fly/v2ray-core), [Xray-core](https://github.com/XTLS/Xray-core) and [Trojan-Go](https https://github.com/p4gefau1t/trojan-go).

- **geoip.dat**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip.dat)
- **geoip.dat.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip.dat.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip.dat.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip.dat.sha256sum )
- **geoip-only-cn-private.dat** (Lite version of GeoIP, only contains `geoip:cn` and `geoip:private`):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only-cn-private.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only-cn -private.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-only-cn-private.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip -only-cn-private.dat)
- **geoip-only-cn-private.dat.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only-cn-private.dat.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only -cn-private.dat.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-only-cn-private.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release /geoip-only-cn-private.dat.sha256sum)
- **geoip-asn.dat** (Lite version of GeoIP, containing only the above added categories):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn.dat )
- **geoip-asn.dat.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat.sha256sum )
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn .dat.sha256sum)
- **cn.dat** (Lite version of GeoIP, contains only `geoip:cn`):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/cn.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/cn.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/cn.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/cn.dat)
- **cn.dat.sha256sum**:
   - [https://raw.githubusercontent.com/Loyalsoldier/g
