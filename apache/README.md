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
