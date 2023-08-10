# 186526 Network BGP Communites

## Well known BGP Communities

| Community      | Description  | Action                                                             |
| -------------- | ------------ | ------------------------------------------------------------------ |
| (65535, 65281) | No Export    | Prefix should not be exported outside of 186526 Network (AS200536) |
| (65535, 65282) | No Advertise | Prefix should not be exported outside of this PoP                  |
| (65535, 65283) | Local AS     | Prefix should not be exported outside of this region               |
| (65535, 666)   | Blackhole    | Prefix should be blackholed at our PoP                             |

## Specific BGP Communities

> 186526 Network implements large BGP communities.

### System-controllable Community

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

### User-controllable Community

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

| Name                      | Location                  | Code | Type | Operational | IPv6 Address for Test |
| ------------------------- | ------------------------- | ---- | ---- | ----------- | --------------------- |
| EMEA                      |
| `core.de-fra1.186526.net` | Frankfurt am Main, DE     | 101  | Core | ✓           | 2a06:a005:28f1::1     |
| `core.nl-ams2.186526.net` | Amsterdam, NL             | 103  | Core | ✓           | 2a06:a005:28f3::2     |
| `core.nl-ams1.186526.net` | Amsterdam, NL             | 103  | Core | ✓           | 2a06:a005:28f3::1     |
| `core.lu-lux1.186526.net` | Roost, LU                 | 104  | Core | ✓           | 2a06:a005:28f4::1     |
| `edge.ae-dxb1.186526.net` | Dubai, AE                 | 601  | Edge | ✓           | 2a0a:6040:a901::1     |
| America                   |
| `core.us-iad1.186526.net` | Ashburn, VA, US           | 201  | Core | ✓           | 2a06:a005:2921::1     |
| `core.us-sjc1.186526.net` | Fremont, CA, US           | 221  | Core | ✓           | 2a06:a005:2922::1     |
| `edge.us-sjc2.186526.net` | San Jose, CA, US          | 221  | Edge | ✓           | 2a06:a005:2922::2     |
| `edge.us-lax1.186526.net` | Los Angeles, CA, US       | 222  | Edge | ✓           | 2a06:a005:2923::1     |
| `core.us-sea1.186526.net` | Seattle, WA, US           | 223  | Core |             | 2a06:a005:2924::1     |
| `core.us-nyc1.186526.net` | New York, NY, US          | 202  | Core | ✓           | 2a06:a005:2925::1     |
| `core.us-mci1.186526.net` | North Kansas City, MO, US | 211  | Core | ✓           | 2a06:a005:2926::1     |
| `edge.br-sao1.186526.net` | Sao Paulo, BR             | 241  | Edge | ✓           | 2a06:a005:2960::1     |
| APAC                      |
| `core.cn-hkg1.186526.net` | Hong Kong SAR             | 401  | Core | ✓           | 2a06:a005:1700::1     |
| `edge.cn-hkg2.186526.net` | Hong Kong SAR             | 401  | Edge | ✓           | 2a06:a005:1708::1     |
| `edge.cn-tpe1.186526.net` | Taipei, CN                | 402  | Edge | ✓           | 2a06:a005:2950::1     |
| `edge.jp-tyo1.186526.net` | Tokyo, JP                 | 403  | Edge | ✓           | 2a06:a005:2940::1     |
| `edge.kr-yny1.186526.net` | Chuncheon, KR             | 404  | Edge | ✓           | 2a06:a005:29d1::1     |
| `core.sg-sin1.186526.net` | Singapore                 | 411  | Core | ✓           | 2a06:a005:2930::1     |
| `edge.sg-sin1.186526.net` | Singapore                 | 411  | Edge | ✓           | 2a06:a005:2930::2     |
| `core.au-syd1.186526.net` | Sydney, AU                | 501  | Core | ✓           | 2a06:a005:f80::1      |

<!-- | China Mainland            |
| `core.cn-pek1.186526.net` | Beijing, CN               | 431  | Core |             | 2a06:a005:2910::1     |
| `edge.cn-sjw1.186526.net` | Shijiazhuang, CN          | 431  | Edge |             | 2a06:a005:2910:1::1   |
| `edge.cn-ctu1.186526.net` | Chengdu, CN               | 432  | Edge |             | 2a06:a005:2911::1     |
| `core.cn-can1.186526.net` | Guangzhou, CN             | 433  | Core | ✓           | 2a06:a005:2912::1     |
| `core.cn-wuh1.186526.net` | Wuhan, CN                 | 434  | Core | ✓           | 2a06:a005:2913::1     |
| `edge.cn-csx1.186526.net` | Changsha, CN              | 435  | Edge | ✓           | 2a06:a005:2914::1     |
| `edge.cn-tao1.186526.net` | Qingdao, CN               | 438  | Edge | ✓           | 2a06:a005:2915::1     |
| `edge.cn-cgo1.186526.net` | Zhengzhou, CN             | 437  | Edge | ✓           | 2a06:a005:2916::1     |
| `edge.cn-wuh2.186526.net` | Wuhan, CN                 | 434  | Edge | ✓           | 2a06:a005:2917::1     |
| `core.cn-csx2.186526.net` | Changsha, CN              | 435  | Core |             | 2a06:a005:2918::1     | -->
