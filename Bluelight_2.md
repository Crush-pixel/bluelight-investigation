## Bluelight 2


All campaigns I've seen from this operator follow a similar structure, so I won't completely replicate the Bluelight 1 investigation. The purpose is to compare and contrast.


#### Header Layer

| Received Date     | Mon, 17 Aug 2026 02:41:29 -0700 (PDT)                                                                    |
| ----------------- | -------------------------------------------------------------------------------------------------------- |
| SPF               | google.com: domain of  return@sb034.kreatifdesain.my.id designates ==37.59.229.131== as permitted sender |
| Return Path       | return@sb034.kreatifdesain.my.id                                                                         |
| Received          | from docs.google.com (dashboard.freedommobile.ca. [==37.59.229.131==])                                   |
| Received          | from efianalytics.com (efianalytics.com. ==216.244.76.116==)                                             |
| Message ID        | 64884-myemail@E8A2MgM.ixn                                                                             |
| X-Original-Sender | <myemail@gmail.com>                                                                                  |
| X-Originating-IP  | ==217.18.210.147==                                                                                       |
| List-Unsubscribe  | http://E8A2MgM.ixn/LEAVE=To                                                                              |
| Date              | Mon, 17 Aug 2026 11:23:07 +0200                                                                          |
| Subject           | ⛔️ Warning! Your Cloud Storage Is Full                                                                   |
| Sender            | myemail@13PU.sb034.kreatifdesain.my.id                                                                   |


#### DNS Layer 


| Domain                                                            | IP                                                    | Notes                                                                                                                                                                                                                           | IP Info                                                                                                                                                                                                                                                                                                                  |
| ----------------------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| sb034.kreatifdesain.<br>my.id<br><br>v=spf1 a:api.netresolve.help |                                                       | No A or TXT records                                                                                                                                                                                                             | <br>                                                                                                                                                                                                                                                                                                                     |
| promos.clarks.com (identified as freedommoblile.ca in the header) | ==37.59.229.131==                                     | Reverse lookup returns promos.clarks.com, which has a CNAME pointing to promosclarks.com, which was acquired by the operators June of 2026 in what seems to be a dangling CNAME attack. [Dangling CNAMES](Dangling_CNAMEs.md)<br>          | "ip": "37.59.229.131",<br>  "hostname": "social.crunch.com",<br>  "city": "Gravelines",<br>  "region": "Hauts-de-France",<br>  "country": "FR",<br>  "loc": "50.9865,2.1281",<br>  "org": "AS16276 OVH SAS",<br>  "postal": "59820",<br>  "timezone": "Europe/Paris",<br>  "readme": "https://ipinfo.io/missingauth"<br> |
| efianalytics.com                                                  | ==216.244.76.116 (forged IP) **==  ==132.148.22.170== | Forged record. Reverse lookup for the forged IP leads to 116.wowrack.com, but a forward lookup for wowrack returns a different address. The chain leads down an obfuscation rabbit hole. The second IP is the A record for efi. | "ip": "216.244.76.116",<br>  "hostname": "116.wowrack.com",<br>  "city": "Tukwila",<br>  "region": "Washington",<br>  "country": "US",<br>  "loc": "47.4740,-122.2610",<br>  "org": "AS27323 Wowrack.com",<br>  "postal": "98178",<br>  "timezone": "America/Los_Angeles",<br>                                           |
| hostingdunyam.<br>com.tr                                          | ==217.18.210.147==                                    | Likely a forged entry. Maps to a Turkish web hosting provider                                                                                                                                                                   | "ip": "217.18.210.147",<br>  "hostname": "hostingdunyam.com.tr",<br>  "city": "Istanbul",<br>  "region": "Istanbul",<br>  "country": "TR",<br>  "loc": "41.0138,28.9497",<br>  "org": "AS212219 HOSTING DUNYAM",<br>  "postal": "34096",<br>  "timezone": "Europe/Istanbul",<br>                                         |



