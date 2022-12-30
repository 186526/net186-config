# 186526 Network (AS200536)

[![Build Status](https://ci.186526.xyz/api/badges/186526/net186-config/status.svg)](https://ci.186526.xyz/186526/net186-config)
![Bird Version Needed](https://img.shields.io/badge/bird-%3E%3D%202.0.8-blue)

- Experimental global network
- Operated by 186526 (https://t.me/real186526)

## Peering

186526 Network have an open peer policy. You can peer with us through our listed IX in [PeeringDB](https://www.peeringdb.com/net/31778) or through IP tunneling under IPv4.

For your convenience, here are more info about peering.

- ASN: `200536`
- AS-SET: `RIPE::AS-NET186`
- Suggested IPv6 Prefix limit: `100`

## Contact

To get in touch with me, please send mail to the following mailboxes.

- Abuse: `abuse@186526.xyz`
- NOC: `noc@186526.xyz`

## BGP Communities

### Well known BGP Communities

| Community      | Description  | Action                                                              |
| -------------- | ------------ | ------------------------------------------------------------------- |
| (65535, 65281) | No Export    | Prefix should not be exported outside of 186526 Network (LOCAL_ASN) |
| (65535, 65282) | No Advertise | Prefix should not be exported outside of this PoP                   |
| (65535, 65283) | Local AS     | Prefix should not be exported outside of this region                |
| (65535, 666)   | Blackhole    | Prefix should be blackholed at our PoP                              |

### Specific BGP Communities

> 186526 Network implements large BGP communities.

#### System-controllable Community

| Community                       | Description                                             |
| ------------------------------- | ------------------------------------------------------- |
| (LOCAL_ASN, 110, 0)             | Route learn from peer                                   |
| (LOCAL_ASN, 110, 1)             | Route learn from IX                                     |
| (LOCAL_ASN, 110, 2)             | Route learn from direct peer                            |
| (LOCAL_ASN, 110, 10)            | Route learn from upstream                               |
| (LOCAL_ASN, 110, 20)            | Route learn from downstream                             |
| (LOCAL_ASN, 110, 30)            | Route from 186526 Network                               |
| (LOCAL_ASN, 120, `this PoP`)    | Route learn on `this PoP`                               |
| (LOCAL_ASN, 121, `this region`) | Route learn in `this region`                            |
| (LOCAL_ASN, 122, `this region`) | Route is passed through `this region` in 186526 Network |

#### User-controllable Community

| Community                       | Action                                                                           |
| ------------------------------- | -------------------------------------------------------------------------------- |  
| (LOCAL_ASN, 0, 665)             | Prefix should only be announced, not written to our routing table                |
| (LOCAL_ASN, 0, 666)             | Prefix should be blackholed at our PoP                                           |
| (LOCAL_ASN, 1, 0)               | Prefix should not be exported to all upstream                                    |
| (LOCAL_ASN, 1, 1)               | Prefix should not be exported to all peers                                       |
| (LOCAL_ASN, 1, 2)               | Prefix should not be exported to all downstream                                  |
| (LOCAL_ASN, 2, `ASN`)           | Prefix should not be exported to all `ASN` BGP sessions                          |
| (LOCAL_ASN, 3, `this region`)   | Prefix should not be exported outside 186526 Network in `this region`            |
| (LOCAL_ASN, 115, 1)             | Route should be prepend 1x outside 186526 Network                                |
| (LOCAL_ASN, 115, 3)             | Route should be prepend 3x outside 186526 Network                                |
| (LOCAL_ASN, 115, 5)             | Route should be prepend 5x outside 186526 Network                                |
| (LOCAL_ASN, 125, `this PoP`)    | Route should not be exported on `this PoP` to other PoPs in 186526 Network       |
| (LOCAL_ASN, 126, `this region`) | Route should not be exported in `this region` to other regions in 186526 Network |


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

| Name    | Location              | Code | Type |
| ------- | --------------------- | ---- | ---- |
| Europe  | ----                  | ---- |
| de-fra1 | Frankfurt am Main, DE | 101  | Edge |
| uk-lhr1 | London, GB            | 102  | Edge |
| nl-ams1 | Amsterdam, NL         | 103  | Core |
| lu-lux1 | Roost, LU             | 104  | Core |
| America | ----                  | ---- |
| us-iad1 | Ashburn, VA, US       | 201  | Core |
| us-sjc1 | Fremont, CA, US       | 221  | Core |
| us-lax1 | Los Angeles, CA, US   | 222  | Edge |
| us-sea1 | Seattle, CA, US       | 223  | Core |
| br-gru1 | Sao Paulo, BR         | 241  | Edge |
| APAC    | ----                  | ---- |
| cn-hkg1 | Hong Kong SAR         | 401  | Core |
| cn-tpe1 | Taipei, CN            | 402  | Edge |
| jp-tyo1 | Tokyo, JP             | 403  | Edge |
| kr-icn1 | Chuncheon, KR         | 404  | Edge |
| sg-sin1 | Singapore             | 410  | Core |
| cn-pek1 | Beijing, CN           | 431  | Core |
| cn-pek2 | Beijing, CN           | 432  | Edge |
| cn-can1 | Guangzhou, CN         | 433  | Core |
| cn-csx1 | Changsha, CN          | 434  | Edge |
| cn-she1 | Shenyang, CN          | 435  | Edge |
| cn-cgo1 | Zhengzhou, CN         | 436  | Edge |
| au-syd1 | Sydney, AU            | 501  | Core |