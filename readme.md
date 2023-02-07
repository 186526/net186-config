---
permalink: /
---

# 186526 Network

![logo](logo/dark.svg)

[![Build Status](https://ci.186526.xyz/api/badges/186526/net186-config/status.svg)](https://ci.186526.xyz/186526/net186-config)
[![Bird Version](https://img.shields.io/badge/bird-%3E%3D%202.0.10-blue)](https://git.186526.xyz/186526/net186-config)
[![status](https://img.shields.io/badge/status-operational-sucess)](https://uptime.186526.net)
[![looking-glass](https://img.shields.io/badge/looking%20glass-available%20at%20lg.186526.net-blue)](https://lg.186526.net/)

- AS200536, aka Sunoaki Network
- Experimental global network
- Operated by 186526 (Bo Xu) [@real186526](https://t.me/real186526), sponsored by Sunoaki Network LLC.

## Peering

186526 Network have an open peer policy. You can peer with us through our listed IX in [PeeringDB](https://www.peeringdb.com/net/31778) or through IP tunneling under IPv4.

For your convenience, here are more info about peering.

- ASN: `200536`
- AS-SET: `RIPE::AS-NET186`
- Suggested IPv6 Prefix limit: `100`

### Transit

186526 network can provide free transit in some places. If you want to know more, please feel free to ask us.

## Contact

To get in touch with me, please send mail to the following mailboxes.

- Abuse: `abuse@186526.xyz`
- NOC: `noc@186526.xyz`

## BGP Communities

### Well known BGP Communities

| Community      | Description  | Action                                                             |
| -------------- | ------------ | ------------------------------------------------------------------ |
| (65535, 65281) | No Export    | Prefix should not be exported outside of 186526 Network (AS200536) |
| (65535, 65282) | No Advertise | Prefix should not be exported outside of this PoP                  |
| (65535, 65283) | Local AS     | Prefix should not be exported outside of this region               |
| (65535, 666)   | Blackhole    | Prefix should be blackholed at our PoP                             |

### Specific BGP Communities

> 186526 Network implements large BGP communities.

#### System-controllable Community

| Community                    | Description                                             |
| ---------------------------- | ------------------------------------------------------- |
| (200536, 110, 0)             | Route learn from peer                                   |
| (200536, 110, 1)             | Route learn from IX                                     |
| (200536, 110, 2)             | Route learn from direct peer                            |
| (200536, 110, 10)            | Route learn from upstream                               |
| (200536, 110, 20)            | Route learn from downstream                             |
| (200536, 110, 30)            | Route from 186526 Network                               |
| (200536, 120, `this PoP`)    | Route learn on `this PoP`                               |
| (200536, 121, `this region`) | Route learn in `this region`                            |
| (200536, 122, `this region`) | Route is passed through `this region` in 186526 Network |

#### User-controllable Community

| Community                    | Action                                                                           |
| ---------------------------- | -------------------------------------------------------------------------------- |
| (200536, 0, 665)             | Prefix should only be announced, not written to our routing table                |
| (200536, 0, 666)             | Prefix should be blackholed at our PoP                                           |
| (200536, 1, 0)               | Prefix should not be exported to all upstream                                    |
| (200536, 1, 1)               | Prefix should not be exported to all peers                                       |
| (200536, 1, 2)               | Prefix should not be exported to all downstream                                  |
| (200536, 2, `ASN`)           | Prefix should not be exported to all `ASN` BGP sessions                          |
| (200536, 3, `this region`)   | Prefix should not be exported outside 186526 Network in `this region`            |
| (200536, 115, 1)             | Route should be prepend 1x outside 186526 Network                                |
| (200536, 115, 3)             | Route should be prepend 3x outside 186526 Network                                |
| (200536, 115, 5)             | Route should be prepend 5x outside 186526 Network                                |
| (200536, 125, `this PoP`)    | Route should not be exported on `this PoP` to other PoPs in 186526 Network       |
| (200536, 126, `this region`) | Route should not be exported in `this region` to other regions in 186526 Network |

## Region & PoP

### Regions

| Name                               | Code |
| ---------------------------------- | ---- |
| Europe                             | 100  |
| East Coast of North America        | 200  |
| Central North America              | 210  |
| West Coast of North America        | 220  |
| Central America                    | 230  |
| Eastern South America              | 240  |
| West South America                 | 250  |
| North Africa                       | 300  |
| Southern Africa                    | 310  |
| East Asia (without China mainland) | 400  |
| Southeast Asia                     | 410  |
| South Asia                         | 420  |
| China mainland                     | 430  |
| Oceania                            | 500  |
| Middle East                        | 600  |

### PoP

| Name           | Location              | Code | Type | Operational |
| -------------- | --------------------- | ---- | ---- | ----------- |
| EMEA           |
| de-fra1        | Frankfurt am Main, DE | 101  | Core | ✓           |
| de-fra2        | Frankfurt am Main, DE | 101  | Core | ✓           |
| uk-lhr1        | London, GB            | 102  | Edge | ✓           |
| nl-ams1        | Amsterdam, NL         | 103  | Core | ✓           |
| lu-lux1        | Roost, LU             | 104  | Core | ✓           |
| de-hoq1        | Dusseldorf, DE        | 105  | Edge | ✓           |
| ae-dxb1        | Dubai, AE             | 601  | Edge | ✓           |
| America        |
| us-iad1        | Ashburn, VA, US       | 201  | Core | ✓           |
| us-sjc1        | Fremont, CA, US       | 221  | Core | ✓           |
| us-lax1        | Los Angeles, CA, US   | 222  | Edge | ✓           |
| us-sea1        | Seattle, CA, US       | 223  | Core | ✓           |
| br-sao1        | Sao Paulo, BR         | 241  | Edge | ✓           |
| APAC           |
| cn-hkg1        | Hong Kong SAR         | 401  | Core | ✓           |
| cn-hkg2        | Hong Kong SAR         | 401  | Edge | ✓           |
| cn-tpe1        | Taipei, CN            | 402  | Edge | ✓           |
| jp-tyo1        | Tokyo, JP             | 403  | Edge | ✓           |
| kr-yny1        | Chuncheon, KR         | 404  | Edge | ✓           |
| jp-osa1        | Osaka, JP             | 405  | Edge | ✓           |
| kr-icn1        | Seoul, KR             | 406  | Edge |
| sg-sin1        | Singapore             | 411  | Core | ✓           |
| sg-sin2        | Singapore             | 412  | Edge |
| in-bom1        | Mumbai, IN            | 421  | Edge |
| China Mainland |
| cn-pek1        | Beijing, CN           | 431  | Core | ✓           |
| cn-pek2        | Beijing, CN           | 431  | Edge |
| cn-ctu1        | near Chengdu, China   | 432  | Edge | ✓           |
| cn-can1        | Guangzhou, CN         | 433  | Core | ✓           |
| cn-wuh1        | Wuhan, CN             | 434  | Core | ✓           |
| cn-wuh2        | Wuhan, CN             | 434  | Edge | ✓           |
| cn-csx1        | Changsha, CN          | 435  | Edge |
| cn-csx2        | Changsha, CN          | 435  | Edge |
| cn-cgo1        | Zhengzhou, CN         | 437  | Edge | ✓           |
| cn-tao1        | Qingdao, CN           | 438  | Edge | ✓           |
| au-syd1        | Sydney, AU            | 501  | Core | ✓           |
