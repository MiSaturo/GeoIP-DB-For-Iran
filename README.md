# Geo IP DB for Iran

# Introduction

This project automatically generates GeoIP files every Thursday, and provides a command line interface (CLI) for users to customize GeoIP files, including but not limited to V2Ray dat format routing rule file `geoip.dat` and MaxMind mmdb format file `Country.mmdb`.

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
         "geoip:ir",
         "geoip:private",
         "ext:ir.dat:ir",
         "ext:private.dat:private",
         "ext:geoip-only-ir-private.dat:ir",
         "ext:geoip-only-ir-private.dat:private"
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

Use the reference configuration of this project's `.mmdb` format file in [Leaf](https://github.com/eycorsican/leaf), see [Official README](https://github.com/eycorsican/leaf/blob/master/README.zh.md#geoip).

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
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip.dat.sha256sum)
- **geoip-only-ir-private.dat** (Lite version of GeoIP, only contains `geoip:ir` and `geoip:private`):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only-ir-private.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only-ir-private.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-only-ir-private.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-only-ir-private.dat)
- **geoip-only-ir-private.dat.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only-ir-private.dat.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-only-ir-private.dat.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-only-ir-private.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-only-ir-private.dat.sha256sum)
- **geoip-asn.dat** (Lite version of GeoIP, containing only the above added categories):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn.dat)
- **geoip-asn.dat.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/geoip-asn.dat.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/geoip-asn.dat.sha256sum)
- **ir.dat** (Lite version of GeoIP, contains only `geoip:ir`):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/ir.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/ir.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/ir.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/ir.dat)
- **ir.dat.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/ir.dat.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/ir.dat.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/ir.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/ir.dat.sha256sum)
- **private.dat** (Lite version of GeoIP, only contains `geoip:private`):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/private.dat](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/private.dat)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/private.dat](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/private.dat)
- **private.dat.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/private.dat.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/private.dat.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/private.dat.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/private.dat.sha256sum)

### MaxMind mmdb format file

> Available for [Clash](https://github.com/Dreamacro/clash) and [Leaf](https://github.com/eycorsican/leaf).

- **Country.mmdb**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country.mmdb](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country.mmdb)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country.mmdb](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country.mmdb)
- **Country.mmdb.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country.mmdb.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country.mmdb.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country.mmdb.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country.mmdb.sha256sum)
- **Country-only-ir-private.mmdb** (Lite version of GeoIP, only contains `GEOIP,IR` and `GEOIP,PRIVATE`):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-only-ir-private.mmdb](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-only-ir -private.mmdb)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-only-ir-private.mmdb](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-only-ir-private.mmdb)
- **Country-only-ir-private.mmdb.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-only-ir-private.mmdb.sha256sum](https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-only-ir-private.mmdb.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-only-ir-private.mmdb.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-only-ir-private.mmdb.sha256sum)
- **Country-asn.mmdb** (Lite version of GeoIP, only contains the above added categories):
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-asn.mmdb(https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-asn.mmdb)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-asn.mmdb](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-asn.mmdb)
- **Country-asn.mmdb.sha256sum**:
   - [https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-asn.mmdb.sha256sum(https://raw.githubusercontent.com/MiSaturo/GeoIP-DB-For-Iran/release/Country-asn.mmdb.sha256sum)
   - [https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-asn.mmdb.sha256sum](https://cdn.jsdelivr.net/gh/MiSaturo/GeoIP-DB-For-Iran@release/Country-asn.mmdb.sha256sum)

## Custom GeoIP file

GeoIP files can be customized in several ways:

- **Online generation**: [Fork](https://github.com/MiSaturo/GeoIP-DB-For-Iran/fork) After this warehouse, modify the configuration file `config.json` and GitHub Workflow `.github/workflows in your own warehouse/build.yml`
- **local generation**:
   - Install [Golang](https://golang.org/dl/) and [Git](https://git-scm.com)
   - Pull project code: `git clone https://github.com/MiSaturo/GeoIP-DB-For-Iran.git`
   - Enter the project root directory: `cd geoip`
   - Modify the configuration file `config.json`
   - Run the code: `go run./`

**Special Note:**

- **Online Generation**: [Fork](https://github.com/MiSaturo/GeoIP-DB-For-Iran/fork) After this project, if you need to use the MaxMind GeoLite2 Country CSV data file, you need to use **[Settings] in your warehouse Add a secret named **MAXMIND_GEOLITE2_LICENSE** to the **[Secrets]** page of the ** tab, otherwise GitHub Actions will fail to run. The value of this secret is the LICENSE KEY of the MAXMIND account. After [**registering a MAXMIND account**](https://www.maxmind.com/en/geolite2/signup), go to the [**personal account management page**] ](https://www.maxmind.com/en/account) generated in **[My License Key]** under the **[Services]** item on the left sidebar.
- **Local generation**: If you need to use the MaxMind GeoLite2 Country CSV data file (`GeoLite2-Country-CSV.zip`), you need to download it from MaxMind in advance, or from the project [release branch](https://github. com/MiSaturo/GeoIP-DB-For-Iran/tree/release)[Download](https://github.com/MiSaturo/GeoIP-DB-For-Iran/raw/release/GeoLite2-Country-CSV.zip), and extract it to a directory named `geolite2`.

### Concept analysis

This project has two concepts: `input` and `output`. `input` refers to the data source (data source) and its input format, and `output` refers to the destination of the data (data destination) and its output format. The role of the CLI is to aggregate all data sources provided by the user by reading the options in the configuration file, deduplicate them, convert them to the target format, and output them to a file.

These two concepts are notable: `input` and `output`. The `input` is the data source and its input format, whereas the `output` is the destination of the converted data and its output format. What the CLI does is to aggregate all input format data, then convert them to output format and write them to GeoIP files by using the options in the config file.

### Supported formats

For configuration options supported by each format, see the [`config-example.json`](https://github.com/MiSaturo/GeoIP-DB-For-Iran/blob/HEAD/config-example.json) file of this project.

Supported `input` input formats:

- **text**: plaintext IP and CIDR (eg: `1.1.1.1` or `1.0.0.0/24`)
- **private**: LAN and private network CIDR (eg: `192.168.0.0/16` and `127.0.0.0/8`)
- **cutter**: used to crop the data in the previous step
- **v2rayGeoIPDat**: V2Ray GeoIP dat format (`geoip.dat`)
- **maxmindMMDB**: MaxMind mmdb data format (`GeoLite2-Country.mmdb`)
- **maxmindGeoLite2CountryCSV**: MaxMind GeoLite2 country CSV data (`GeoLite2-Country-CSV.zip`)
- **clashRuleSetClassical**: [classical type of Clash RuleSet](https://github.com/Dreamacro/clash/wiki/premium-core-features#classical)
- **clashRuleSet**: [Clash RuleSet of type ipcidr](https://github.com/Dreamacro/clash/wiki/premium-core-features#ipcidr)
- **surgeRuleSet**: [Surge RuleSet](https://manual.nssurge.com/rule/ruleset.html)

Supported `output` output formats:

- **text**: plain text CIDR (eg: `1.0.0.0/24`)
- **v2rayGeoIPDat**: V2Ray GeoIP dat format (`geoip.dat`, suitable for [V2Ray](https://github.com/v2fly/v2ray-core), [Xray-core](https://github.com/XTLS/Xray-core) and [Trojan-Go](https://github.com/p4gefau1t/trojan-go))
- **maxmindMMDB**: MaxMind mmdb data format (`GeoLite2-Country.mmdb` for [Clash](https://github.com/Dreamacro/clash) and [Leaf](https://github.com/eycorsican/leaf))
- **clashRuleSetClassical**: [classical type of Clash RuleSet](https://github.com/Dreamacro/clash/wiki/premium-core-features#classical)
- **clashRuleSet**: [Clash RuleSet of type ipcidr](https://github.com/Dreamacro/clash/wiki/premium-core-features#ipcidr)
- **surgeRuleSet**: [Surge RuleSet](https://manual.nssurge.com/rule/ruleset.html)

### Precautions

Due to the limitation of the MaxMind mmdb file format, when the IP or CIDR data of different lists overlap or overlap, the IP or CIDR data of the list written later will overwrite (overwrite) the data of the previously written list. For example, IP `1.1.1.1` belongs to both list `AU` and list `Cloudflare`. If `Cloudflare` is written after `AU`, the IP `1.1.1.1` belongs to the list `Cloudflare`.

In order to ensure that certain specified lists and modified lists must include all IP or CIDR data belonging to it, the option `overwriteList` can be added to the configuration of `output` output format as `maxmindMMDB`, the list specified in this option will be Write one by one at the end, the last item in the list has the highest priority. If the option `wantedList` is set, there is no need to set `overwriteList`. The list specified in `wantedList` will be written one by one at the end, and the last item in the list has the highest priority.

## CLI function display

The CLI can be installed directly via `go install -v github.com/MiSaturo/GeoIP-DB-For-Iran@latest`.

```bash
$./geoip -h
Usage of./geoip:
   -c string
     URI of the JSON format config file, support both local file path and remote HTTP(S) URL (default "config.json")
   -l List all available input and output formats

$./geoip -c config.json
2021/08/29 12:11:35 ✅ [v2rayGeoIPDat] geoip.dat --> output/dat
2021/08/29 12:11:35 ✅ [v2rayGeoIPDat] geoip-only-ir-private.dat --> output/dat
2021/08/29 12:11:35 ✅ [v2rayGeoIPDat] geoip-asn.dat --> output/dat
2021/08/29 12:11:35 ✅ [v2rayGeoIPDat] ir.dat --> output/dat
2021/08/29 12:11:35 ✅ [v2rayGeoIPDat] private.dat --> output/dat
2021/08/29 12:11:39 ✅ [maxmindMMDB] Country.mmdb --> output/maxmind
2021/08/29 12:11:39 ✅ [maxmindMMDB] Country-only-ir-private.mmdb --> output/maxmind
2021/08/29 12:11:39 ✅ [text] netflix.txt --> output/text
2021/08/29 12:11:39 ✅ [text] telegram.txt --> output/text
2021/08/29 12:11:39 ✅ [text] ir.txt --> output/text
2021/08/29 12:11:39 ✅ [text] cloudflare.txt --> output/text
2021/08/29 12:11:39 ✅ [text] cloudfront.txt --> output/text
2021/08/29 12:11:39 ✅ [text] facebook.txt --> output/text
2021/08/29 12:11:39 ✅ [text] fastly.txt --> output/text

$./geoip -l
All available input formats:
   - v2rayGeoIPDat (Convert V2Ray GeoIP dat to other formats)
   - maxmindMMDB (Convert MaxMind mmdb database to other formats)
   - maxmindGeoLite2CountryCSV (Convert MaxMind GeoLite2 country CSV data to other formats)
   - private (Convert LAN and private network CIDR to other formats)
   - text (Convert plaintext IP & CIDR to other formats)
   - clashRuleSetClassical (Convert classical type of Clash RuleSet to other formats (just processing IP & CIDR lines))
   - clashRuleSet (Convert ipcidr type of Clash RuleSet to other formats)
   - surgeRuleSet (Convert Surge RuleSet to other formats (just processing IP & CIDR lines))
   - cutter (Remove data from previous steps)
   - test (Convert specific CIDR to other formats (for test only))
All available output formats:
   - v2rayGeoIPDat (Convert data to V2Ray GeoIP dat format)
   - maxmindMMDB (Convert data to MaxMind mmdb database format)
   -clashRuleSetClassical (Convert data to classical type of Clash RuleSet)
   -clashRuleSet (Convert data to ipcidr type of Clash RuleSet)
   - surgeRuleSet (Convert data to Surge RuleSet)
   - text (Convert data to plaintext CIDR format)
```

## License

[CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/)

This product includes GeoLite2 data created by MaxMind, available from [MaxMind](http://www.maxmind.com).

## Project Star number growth trend

[![Stargazers over time](https://starchart.cc/MiSaturo/GeoIP-DB-For-Iran.svg)](https://starchart.cc/MiSaturo/GeoIP-DB-For-Iran)
