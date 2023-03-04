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

| Name    | Location              | Code | Type | Operational |
| ------- | --------------------- | ---- | ---- | ----------- |
| EMEA    |
| de-fra1 | Frankfurt am Main, DE | 101  | Core | ✓           |
| de-fra2 | Frankfurt am Main, DE | 101  | Core | ✓           |
| uk-lhr1 | London, GB            | 102  | Edge | ✓           |
| nl-ams1 | Amsterdam, NL         | 103  | Core | ✓           |
| lu-lux1 | Roost, LU             | 104  | Core | ✓           |
| de-hoq1 | Dusseldorf, DE        | 105  | Edge | ✓           |
| ae-dxb1 | Dubai, AE             | 601  | Edge | ✓           |
| America |
| us-iad1 | Ashburn, VA, US       | 201  | Core | ✓           |
| us-iad2 | Ashburn, VA, US       | 201  | Edge | ✓           |
| us-sjc1 | Fremont, CA, US       | 221  | Core | ✓           |
| us-lax1 | Los Angeles, CA, US   | 222  | Edge | ✓           |
| us-sea1 | Seattle, CA, US       | 223  | Core | ✓           |
| br-sao1 | Sao Paulo, BR         | 241  | Edge | ✓           |
| APAC    |
| cn-hkg1 | Hong Kong SAR         | 401  | Core | ✓           |
| cn-hkg2 | Hong Kong SAR         | 401  | Edge | ✓           |
| cn-tpe1 | Taipei, CN            | 402  | Edge | ✓           |
| jp-tyo1 | Tokyo, JP             | 403  | Edge | ✓           |
| kr-yny1 | Chuncheon, KR         | 404  | Edge | ✓           |
| jp-osa1 | Osaka, JP             | 405  | Edge | ✓           |
| kr-icn1 | Seoul, KR             | 406  | Edge | ✓           |
| sg-sin1 | Singapore             | 411  | Core | ✓           |
| sg-sin2 | Singapore             | 411  | Edge |
| in-bom1 | Mumbai, IN            | 421  | Edge | ✓           |
| au-syd1 | Sydney, AU            | 501  | Core | ✓           |

<!-- | China Mainland |
| cn-pek1        | Beijing, CN           | 431  | Core | ✓           |
| cn-pek2        | Beijing, CN           | 431  | Edge |
| cn-sjw1        | Shijiazhuang, CN      | 431  | Edge | ✓           |
| cn-ctu1        | near Chengdu, CN      | 432  | Edge | ✓           |
| cn-can1        | Guangzhou, CN         | 433  | Core |             |
| cn-wuh1        | Wuhan, CN             | 434  | Core | ✓           |
| cn-wuh2        | Wuhan, CN             | 434  | Edge | ✓           |
| cn-csx1        | Changsha, CN          | 435  | Edge | ✓           |
| cn-csx2        | Changsha, CN          | 435  | Edge |
| cn-cgo1        | Zhengzhou, CN         | 437  | Edge | ✓           |
| cn-tao1        | Qingdao, CN           | 438  | Edge | ✓           | -->
