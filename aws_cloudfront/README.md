### ./view/view_example_data.sx
```jsx
INIT(
  from:t("2020-08-10 00:00:00.000 +0000"),
    to:t("2020-08-10 22:30:00.000 +0000")
);

INCLUDE './aws_utils.sx';

LIST(src:'s3s://spectx-docs/logs/aws_cloudfront/www.smartcyberwise.ai/F13GMIPW293BT2.$yyyy$-$MM$-$dd$-$HH$.*.gz', _tz:'GMT')
| filter(path_time BETWEEN $from[-2 hour] AND $to)
| parse(pattern:$[./aws_cloudfront_pattern.sxp])
| filter(timestamp BETWEEN $from AND $to)
| @@aws_url_decode_text_fields
```

| timestamp                       | location | bytes | ip                | method | host                         | uri           | status | referrer                       | user_agent                                                                                                               | query_string | cookie | result_type | request_id                                               | host_header           | request_protocol | request_bytes | time_taken | xforwarded_for | ssl_protocol | ssl_cipher                  | response_result_type | http_version | fle_status | fle_encrypted_fields | c_port | time_to_first_byte | x_edge_detailed_result_type | sc_content_type            | sc_content_len | sc_range_start | sc_range_end |
|---------------------------------|----------|------:|-------------------|--------|------------------------------|---------------|-------:|--------------------------------|--------------------------------------------------------------------------------------------------------------------------|--------------|--------|-------------|----------------------------------------------------------|-----------------------|------------------|--------------:|-----------:|----------------|--------------|-----------------------------|----------------------|--------------|------------|---------------------:|-------:|-------------------:|-----------------------------|----------------------------|---------------:|---------------:|-------------:|
| `2020‑08‑10 03:03:06.000 +0300` | MIA3‑C3  |   510 | `35.196.197.25`   | GET    | ygeb7h2imqp29.cloudfront.net | /robots.txt   |    200 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Hit         | o6v2QV_yzXI0PyC_FbRcX8higSOPC7zJ4YgmXJ_uogp_cmYCbwnyJw== | www.smartcyberwise.ai | http             |           359 |      0.056 | *null*         | *null*       | *null*                      | Hit                  | HTTP/1.0     | *null*     |               *null* |  50975 |              0.055 | Hit                         | text/plain                 |             76 |         *null* |       *null* |
| `2020‑08‑10 03:03:06.000 +0300` | MIA3‑C3  |   574 | `35.196.197.25`   | GET    | ygeb7h2imqp29.cloudfront.net | /             |    301 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Redirect    | VUajMB0T9ggiHh‑x0Gd4guya9oyX5GPZ7bvyees3DQ_T‑‑VLPvdBqA== | www.smartcyberwise.ai | http             |           349 |        0.0 | *null*         | *null*       | *null*                      | Redirect             | HTTP/1.0     | *null*     |               *null* |  53948 |                0.0 | Redirect                    | text/html                  |            183 |         *null* |       *null* |
| `2020‑08‑10 03:03:06.000 +0300` | MIA3‑C3  |   510 | `35.196.197.25`   | GET    | ygeb7h2imqp29.cloudfront.net | /robots.txt   |    200 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Hit         | wTIK8qG‑QrRMj1XHIDfqrwsWpS8l76LRbmdL‑UE74jUZOOtDBI5ouw== | www.smartcyberwise.ai | https            |           359 |      0.002 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.0     | *null*     |               *null* |  39081 |              0.002 | Hit                         | text/plain                 |             76 |         *null* |       *null* |
| `2020‑08‑10 03:03:07.000 +0300` | MIA3‑C3  | 30593 | `35.196.197.25`   | GET    | ygeb7h2imqp29.cloudfront.net | /             |    200 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Hit         | WofOUW56ktwAOftksS7K6H5WfbV41QPGZ__dIIOEAOUkhCCsBLrmNg== | www.smartcyberwise.ai | https            |           349 |      0.039 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.0     | *null*     |               *null* |  48162 |              0.038 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `2020‑08‑10 03:13:49.000 +0300` | SFO20‑C1 |   500 | `216.218.145.211` | GET    | ygeb7h2imqp29.cloudfront.net | /robots.txt   |    200 | *null*                         | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/45.0.2454.46 Safari/537.36 | *null*       | *null* | Miss        | MUaWaSlMxgc3ZReH3QLK1l34sUL6BGcyr0WJ_VExkWYHno8YT2BpSA== | www.smartcyberwise.ai | https            |           216 |      0.209 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Miss                 | HTTP/1.0     | *null*     |               *null* |  35078 |              0.209 | Miss                        | text/plain                 |             76 |         *null* |       *null* |
| `2020‑08‑10 03:13:50.000 +0300` | SFO20‑C1 | 38058 | `216.218.145.211` | GET    | ygeb7h2imqp29.cloudfront.net | /page_240     |    200 | *null*                         | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/45.0.2454.46 Safari/537.36 | *null*       | *null* | Hit         | x26PmnomSnC2U6QFYVb74kD6eKfvN2qnUeN7QOnFUMPkPFHoOVQ_sQ== | www.smartcyberwise.ai | https            |           214 |      0.003 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.0     | *null*     |               *null* |  35704 |              0.003 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `2020‑08‑10 03:25:47.000 +0300` | SEA19‑C2 | 30642 | `35.185.127.104`  | GET    | ygeb7h2imqp29.cloudfront.net | /             |    200 | https://www.smartcyberwise.ai/ | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:56.0) Gecko/20100101 Firefox/56.0                                           | *null*       | *null* | Hit         | 97‑LYY5LYC‑ui_Vpikwe7MGXPLWG4m9FDaR4uVElzt39Y1oSjR4ZEQ== | www.smartcyberwise.ai | https            |           230 |      0.001 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.1     | *null*     |               *null* |  34808 |              0.001 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `2020‑08‑10 03:25:47.000 +0300` | SEA19‑C2 | 30635 | `35.185.127.104`  | GET    | ygeb7h2imqp29.cloudfront.net | /             |    200 | *null*                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:56.0) Gecko/20100101 Firefox/56.0                                           | *null*       | *null* | Hit         | yfzf2Wgwi1snoBYuvNx96QAIJSZZ0_H1ijU_QYQwte5Y73wFM2hliw== | www.smartcyberwise.ai | https            |           198 |      0.019 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.1     | *null*     |               *null* |  57616 |              0.019 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `2020‑08‑10 03:25:47.000 +0300` | SEA19‑C2 |   575 | `35.185.127.104`  | GET    | ygeb7h2imqp29.cloudfront.net | /             |    301 | *null*                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:56.0) Gecko/20100101 Firefox/56.0                                           | *null*       | *null* | Redirect    | tlPSh2lcrgrIzICjyikB13HujsEzFCgdtdqeh7QEZLpZXcCggIFPpQ== | www.smartcyberwise.ai | http             |           198 |        0.0 | *null*         | *null*       | *null*                      | Redirect             | HTTP/1.1     | *null*     |               *null* |  44920 |                0.0 | Redirect                    | text/html                  |            183 |         *null* |       *null* |
| `2020‑08‑10 03:38:33.000 +0300` | OTP50‑C1 |  9951 | `46.196.34.167`   | GET    | ygeb7h2imqp29.cloudfront.net | /sub/page_171 |    200 | *null*                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:80.0) Gecko/20100101 Firefox/80.0                                           | *null*       | *null* | Miss        | HvylR0AfUEEPKaraOQXTPrXsprs5Xd7MPD80uHhMkHoXsDwMoiKqtQ== | www.smartcyberwise.ai | https            |           224 |      0.164 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Miss                 | HTTP/2.0     | *null*     |               *null* |  50615 |              0.163 | Miss                        | text/html;%20charset=utf‑8 |           9435 |         *null* |       *null* |
....


### ./query_ip_metainfo.sx
```jsx
@[./view/view_default.sx]
| select(ip, cc(ip), asname(ip), geo(ip), *)
```

| ip                | cc | asname                                                   | geo              | timestamp                       | location | bytes | method | host                         | uri           | status | referrer                       | user_agent                                                                                                               | query_string | cookie | result_type | request_id                                               | host_header           | request_protocol | request_bytes | time_taken | xforwarded_for | ssl_protocol | ssl_cipher                  | response_result_type | http_version | fle_status | fle_encrypted_fields | c_port | time_to_first_byte | x_edge_detailed_result_type | sc_content_type            | sc_content_len | sc_range_start | sc_range_end |
|-------------------|----|----------------------------------------------------------|------------------|---------------------------------|----------|------:|--------|------------------------------|---------------|-------:|--------------------------------|--------------------------------------------------------------------------------------------------------------------------|--------------|--------|-------------|----------------------------------------------------------|-----------------------|------------------|--------------:|-----------:|----------------|--------------|-----------------------------|----------------------|--------------|------------|---------------------:|-------:|-------------------:|-----------------------------|----------------------------|---------------:|---------------:|-------------:|
| `35.196.197.25`   | US | AS15169 GOOGLE                                           | 32.8608,‑79.9746 | `2020‑08‑10 03:03:06.000 +0300` | MIA3‑C3  |   510 | GET    | ygeb7h2imqp29.cloudfront.net | /robots.txt   |    200 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Hit         | o6v2QV_yzXI0PyC_FbRcX8higSOPC7zJ4YgmXJ_uogp_cmYCbwnyJw== | www.smartcyberwise.ai | http             |           359 |      0.056 | *null*         | *null*       | *null*                      | Hit                  | HTTP/1.0     | *null*     |               *null* |  50975 |              0.055 | Hit                         | text/plain                 |             76 |         *null* |       *null* |
| `35.196.197.25`   | US | AS15169 GOOGLE                                           | 32.8608,‑79.9746 | `2020‑08‑10 03:03:06.000 +0300` | MIA3‑C3  |   574 | GET    | ygeb7h2imqp29.cloudfront.net | /             |    301 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Redirect    | VUajMB0T9ggiHh‑x0Gd4guya9oyX5GPZ7bvyees3DQ_T‑‑VLPvdBqA== | www.smartcyberwise.ai | http             |           349 |        0.0 | *null*         | *null*       | *null*                      | Redirect             | HTTP/1.0     | *null*     |               *null* |  53948 |                0.0 | Redirect                    | text/html                  |            183 |         *null* |       *null* |
| `35.196.197.25`   | US | AS15169 GOOGLE                                           | 32.8608,‑79.9746 | `2020‑08‑10 03:03:06.000 +0300` | MIA3‑C3  |   510 | GET    | ygeb7h2imqp29.cloudfront.net | /robots.txt   |    200 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Hit         | wTIK8qG‑QrRMj1XHIDfqrwsWpS8l76LRbmdL‑UE74jUZOOtDBI5ouw== | www.smartcyberwise.ai | https            |           359 |      0.002 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.0     | *null*     |               *null* |  39081 |              0.002 | Hit                         | text/plain                 |             76 |         *null* |       *null* |
| `35.196.197.25`   | US | AS15169 GOOGLE                                           | 32.8608,‑79.9746 | `2020‑08‑10 03:03:07.000 +0300` | MIA3‑C3  | 30593 | GET    | ygeb7h2imqp29.cloudfront.net | /             |    200 | *null*                         | ZoominfoBot (zoominfobot at zoominfo dot com)                                                                            | *null*       | *null* | Hit         | WofOUW56ktwAOftksS7K6H5WfbV41QPGZ__dIIOEAOUkhCCsBLrmNg== | www.smartcyberwise.ai | https            |           349 |      0.039 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.0     | *null*     |               *null* |  48162 |              0.038 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `216.218.145.211` | US | AS6939 HURRICANE                                         | 37.751,‑97.822   | `2020‑08‑10 03:13:49.000 +0300` | SFO20‑C1 |   500 | GET    | ygeb7h2imqp29.cloudfront.net | /robots.txt   |    200 | *null*                         | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/45.0.2454.46 Safari/537.36 | *null*       | *null* | Miss        | MUaWaSlMxgc3ZReH3QLK1l34sUL6BGcyr0WJ_VExkWYHno8YT2BpSA== | www.smartcyberwise.ai | https            |           216 |      0.209 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Miss                 | HTTP/1.0     | *null*     |               *null* |  35078 |              0.209 | Miss                        | text/plain                 |             76 |         *null* |       *null* |
| `216.218.145.211` | US | AS6939 HURRICANE                                         | 37.751,‑97.822   | `2020‑08‑10 03:13:50.000 +0300` | SFO20‑C1 | 38058 | GET    | ygeb7h2imqp29.cloudfront.net | /page_240     |    200 | *null*                         | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/45.0.2454.46 Safari/537.36 | *null*       | *null* | Hit         | x26PmnomSnC2U6QFYVb74kD6eKfvN2qnUeN7QOnFUMPkPFHoOVQ_sQ== | www.smartcyberwise.ai | https            |           214 |      0.003 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.0     | *null*     |               *null* |  35704 |              0.003 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `35.185.127.104`  | US | AS15169 GOOGLE                                           | 32.8608,‑79.9746 | `2020‑08‑10 03:25:47.000 +0300` | SEA19‑C2 | 30642 | GET    | ygeb7h2imqp29.cloudfront.net | /             |    200 | https://www.smartcyberwise.ai/ | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:56.0) Gecko/20100101 Firefox/56.0                                           | *null*       | *null* | Hit         | 97‑LYY5LYC‑ui_Vpikwe7MGXPLWG4m9FDaR4uVElzt39Y1oSjR4ZEQ== | www.smartcyberwise.ai | https            |           230 |      0.001 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.1     | *null*     |               *null* |  34808 |              0.001 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `35.185.127.104`  | US | AS15169 GOOGLE                                           | 32.8608,‑79.9746 | `2020‑08‑10 03:25:47.000 +0300` | SEA19‑C2 | 30635 | GET    | ygeb7h2imqp29.cloudfront.net | /             |    200 | *null*                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:56.0) Gecko/20100101 Firefox/56.0                                           | *null*       | *null* | Hit         | yfzf2Wgwi1snoBYuvNx96QAIJSZZ0_H1ijU_QYQwte5Y73wFM2hliw== | www.smartcyberwise.ai | https            |           198 |      0.019 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Hit                  | HTTP/1.1     | *null*     |               *null* |  57616 |              0.019 | Hit                         | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `35.185.127.104`  | US | AS15169 GOOGLE                                           | 32.8608,‑79.9746 | `2020‑08‑10 03:25:47.000 +0300` | SEA19‑C2 |   575 | GET    | ygeb7h2imqp29.cloudfront.net | /             |    301 | *null*                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:56.0) Gecko/20100101 Firefox/56.0                                           | *null*       | *null* | Redirect    | tlPSh2lcrgrIzICjyikB13HujsEzFCgdtdqeh7QEZLpZXcCggIFPpQ== | www.smartcyberwise.ai | http             |           198 |        0.0 | *null*         | *null*       | *null*                      | Redirect             | HTTP/1.1     | *null*     |               *null* |  44920 |                0.0 | Redirect                    | text/html                  |            183 |         *null* |       *null* |
| `46.196.34.167`   | TR | AS47524 Turksat Uydu Haberlesme ve Kablo TV Isletme A.S. | 41.0494,27.3014  | `2020‑08‑10 03:38:33.000 +0300` | OTP50‑C1 |  9951 | GET    | ygeb7h2imqp29.cloudfront.net | /sub/page_171 |    200 | *null*                         | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:80.0) Gecko/20100101 Firefox/80.0                                           | *null*       | *null* | Miss        | HvylR0AfUEEPKaraOQXTPrXsprs5Xd7MPD80uHhMkHoXsDwMoiKqtQ== | www.smartcyberwise.ai | https            |           224 |      0.164 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Miss                 | HTTP/2.0     | *null*     |               *null* |  50615 |              0.163 | Miss                        | text/html;%20charset=utf‑8 |           9435 |         *null* |       *null* |
....


### ./query_stats_by_city_bytes_transferred.sx
```jsx
$location_code(location)=substr($location, 0, 3);

@[./view/view_default.sx]
| select(*, $location_code(location))
| leftjoin(@[./view/view_edge_locations.sx] on location_code)
| select(city, transferred:sum_long(bytes))
| group(city)
| sort(transferred DESC)
```

| city                  | transferred |
|-----------------------|------------:|
| London                |     2391631 |
| Frankfurt             |     2248902 |
| Seattle, WA           |     1638592 |
| Ashburn, VA           |     1626658 |
| Newark, NJ            |     1555899 |
| Paris                 |     1231188 |
| Dallas/Fort Worth, TX |     1205146 |
| Amsterdam             |     1176792 |
| Atlanta, GA           |     1130356 |
| Miami, FL             |     1102959 |
....

### ./query_stats_by_edge_and_ip.sx
```jsx
@[./view/view_default.sx]
| select(location, ip, count(*))
| group(location, ip)
| select(location, uniq_ips:count(*), total_hits:sum_long(count))
| group(location)
| sort(uniq_ips desc)
```

| location | uniq_ips | total_hits |
|----------|---------:|-----------:|
| SEA19‑C2 |       45 |        158 |
| IAD89‑C2 |       34 |        104 |
| FRA50‑C1 |       25 |        182 |
| FRA53‑C1 |       19 |         79 |
| LHR52‑C1 |       15 |         80 |
| ORD51‑C1 |       15 |         44 |
| AMS54‑C1 |       13 |        129 |
| CDG3‑C1  |       13 |         98 |
| GRU1‑C1  |       13 |         23 |
| LHR61‑C1 |       13 |         85 |
....

### ./query_stats_by_edge_latency.sx
```jsx
@[./view/view_default.sx]
| select(location, count(*), min(time_taken), max(time_taken), avg(time_taken), STDDEV(time_taken))
| group(location)
| sort(avg_time_taken)
```
| location | count | min_time_taken | max_time_taken |        avg_time_taken |    stddev_time_taken |
|----------|------:|---------------:|---------------:|----------------------:|---------------------:|
| DUB2‑C1  |     1 |            0.0 |            0.0 |                   0.0 |                  0.0 |
| BOM52‑C1 |     1 |          0.002 |          0.002 | 0.0020000000949949026 |                  0.0 |
| SIN2‑C1  |     1 |          0.005 |          0.005 |  0.004999999888241291 |                  0.0 |
| YTO50‑C2 |     5 |            0.0 |          0.029 |  0.006599999871104956 | 0.012541929284185821 |
| AMS54‑C1 |   129 |            0.0 |           0.26 |  0.006883720923287346 | 0.023613299210061004 |
| LHR52‑C1 |    80 |            0.0 |          0.079 | 0.0077875001894426536 | 0.014154387680538522 |
| MUC50‑C1 |    13 |          0.002 |          0.019 |  0.009923076955601573 | 0.005090211793384546 |
| BRU50‑C1 |    66 |          0.001 |          0.106 |  0.010924242466871598 | 0.016512289585877547 |
| LHR62‑C1 |    38 |          0.001 |          0.076 |  0.011394736834948785 | 0.018507178049834913 |
| IAD79‑C3 |    40 |            0.0 |          0.035 |   0.01177500007324852 | 0.010761964223974744 |
....


### ./query_stats_by_status_range.sx
```jsx
@[./view/view_default.sx]
| select(
  day:timestamp[1 hour],
  total:count(*), 
  status_200:count(status=200),
  status_1xx:count(status between 100 and 199),
  status_2xx:count(status between 200 and 299),
  status_3xx:count(status between 300 and 399),
  status_4xx:count(status between 400 and 499),
  status_5xx:count(status between 500 and 599)
)
| group(day)
| select(*, fail_4xx_ratio:100.0*status_4xx/total)
```
| day                             | total | status_200 | status_1xx | status_2xx | status_3xx | status_4xx | status_5xx |    fail_4xx_ratio |
|---------------------------------|------:|-----------:|-----------:|-----------:|-----------:|-----------:|-----------:|------------------:|
| `2020‑08‑10 03:00:00.000 +0300` |    27 |         24 |          0 |         24 |          3 |          0 |          0 |               0.0 |
| `2020‑08‑10 04:00:00.000 +0300` |    54 |         52 |          0 |         52 |          2 |          0 |          0 |               0.0 |
| `2020‑08‑10 05:00:00.000 +0300` |    19 |         18 |          0 |         18 |          1 |          0 |          0 |               0.0 |
| `2020‑08‑10 06:00:00.000 +0300` |    10 |          6 |          0 |          6 |          3 |          1 |          0 |              10.0 |
| `2020‑08‑10 07:00:00.000 +0300` |   102 |         71 |          0 |         71 |          1 |         30 |          0 | 29.41176470588235 |
| `2020‑08‑10 08:00:00.000 +0300` |    35 |         30 |          0 |         31 |          3 |          0 |          0 |               0.0 |
| `2020‑08‑10 09:00:00.000 +0300` |   101 |         97 |          0 |         97 |          4 |          0 |          0 |               0.0 |
| `2020‑08‑10 10:00:00.000 +0300` |    98 |         88 |          0 |         94 |          4 |          0 |          0 |               0.0 |
| `2020‑08‑10 11:00:00.000 +0300` |   112 |         91 |          0 |         91 |         11 |          7 |          0 |              6.25 |
| `2020‑08‑10 12:00:00.000 +0300` |   440 |        429 |          0 |        431 |          9 |          0 |          0 |               0.0 |
....

### ./query_top_user_agents.sx
```jsx
@[./view/view_default.sx]
| select(count(*), user_agent)
| group(user_agent)
| sort(count DESC)
```
| count | user_agent                                                                                                                              |
|------:|-----------------------------------------------------------------------------------------------------------------------------------------|
|   521 | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.105 Safari/537.36                     |
|   343 | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:79.0) Gecko/20100101 Firefox/79.0                                                          |
|    92 | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.105 Safari/537.36 Edg/84.0.522.52     |
|    89 | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.105 Safari/537.36               |
|    86 | Mozilla/5.0 (Windows NT 5.1; Trident/7.0; rv:11.0) like Gecko                                                                           |
|    63 | Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:79.0) Gecko/20100101 Firefox/79.0                                                            |
|    60 | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.105 Safari/537.36               |
|    56 | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36                     |
|    48 | Mozilla/5.0 (iPhone; CPU iPhone OS 14_0 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/14.0 Mobile/15E148 Safari/604.1 |
|    44 | Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:78.0) Gecko/20100101 Firefox/78.0                                                          |
....

### ./join_with_tor_exit_nodes.sx
```jsx
@[./view/view_default.sx]
| leftjoin(@[../tor_exit_nodes/view_cached.sx] ON left.ip = right.tor_ip)
| filter(tor_ip is not null)
| select(tor_ip, tor_time, tor_id, *)
```
| tor_ip            | tor_time                        | tor_id                                   | timestamp                       | location | bytes | ip                | method | host                         | uri      | status | referrer                           | user_agent                                                                                                             | query_string | cookie | result_type | request_id                                               | host_header           | request_protocol | request_bytes | time_taken | xforwarded_for | ssl_protocol | ssl_cipher                  | response_result_type | http_version | fle_status | fle_encrypted_fields | c_port | time_to_first_byte | x_edge_detailed_result_type | sc_content_type            | sc_content_len | sc_range_start | sc_range_end |
|-------------------|---------------------------------|------------------------------------------|---------------------------------|----------|------:|-------------------|--------|------------------------------|----------|-------:|------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------|--------|-------------|----------------------------------------------------------|-----------------------|------------------|--------------:|-----------:|----------------|--------------|-----------------------------|----------------------|--------------|------------|---------------------:|-------:|-------------------:|-----------------------------|----------------------------|---------------:|---------------:|-------------:|
| `185.220.100.249` | `2020‑09‑09 14:02:54.000 +0300` | 887CAB501A9DB68A2C44EDF98BF50B0304EED8B6 | `2020‑08‑10 21:52:52.000 +0300` | FRA53‑C1 |  1552 | `185.220.100.249` | GET    | ygeb7h2imqp29.cloudfront.net | /page_60 |    404 | https://www.smartcyberwise.ai/page | Mozilla/5.0 (Linux; Android 9; Mi A1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Mobile Safari/537.36 | *null*       | *null* | Error       | TL7zSaPKYDRxzBi02p9NE4PYzxUcEAe1rxIMvVfQ2JtA7u0tE2a2OA== | www.smartcyberwise.ai | https            |           427 |      0.078 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Error                | HTTP/1.1     | *null*     |               *null* |  10524 |              0.078 | Error                       | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `185.220.100.249` | `2020‑09‑09 13:50:43.000 +0300` | CD09CD7C7F8815B37210C7D1A628599C78D22D6D | `2020‑08‑10 21:52:52.000 +0300` | FRA53‑C1 |  1552 | `185.220.100.249` | GET    | ygeb7h2imqp29.cloudfront.net | /page_60 |    404 | https://www.smartcyberwise.ai/page | Mozilla/5.0 (Linux; Android 9; Mi A1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Mobile Safari/537.36 | *null*       | *null* | Error       | TL7zSaPKYDRxzBi02p9NE4PYzxUcEAe1rxIMvVfQ2JtA7u0tE2a2OA== | www.smartcyberwise.ai | https            |           427 |      0.078 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Error                | HTTP/1.1     | *null*     |               *null* |  10524 |              0.078 | Error                       | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `185.220.100.249` | `2020‑08‑21 12:51:38.000 +0300` | *null*                                   | `2020‑08‑10 21:52:52.000 +0300` | FRA53‑C1 |  1552 | `185.220.100.249` | GET    | ygeb7h2imqp29.cloudfront.net | /page_60 |    404 | https://www.smartcyberwise.ai/page | Mozilla/5.0 (Linux; Android 9; Mi A1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Mobile Safari/537.36 | *null*       | *null* | Error       | TL7zSaPKYDRxzBi02p9NE4PYzxUcEAe1rxIMvVfQ2JtA7u0tE2a2OA== | www.smartcyberwise.ai | https            |           427 |      0.078 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Error                | HTTP/1.1     | *null*     |               *null* |  10524 |              0.078 | Error                       | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
| `185.220.100.249` | `2020‑09‑01 08:24:16.000 +0300` | *null*                                   | `2020‑08‑10 21:52:52.000 +0300` | FRA53‑C1 |  1552 | `185.220.100.249` | GET    | ygeb7h2imqp29.cloudfront.net | /page_60 |    404 | https://www.smartcyberwise.ai/page | Mozilla/5.0 (Linux; Android 9; Mi A1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Mobile Safari/537.36 | *null*       | *null* | Error       | TL7zSaPKYDRxzBi02p9NE4PYzxUcEAe1rxIMvVfQ2JtA7u0tE2a2OA== | www.smartcyberwise.ai | https            |           427 |      0.078 | *null*         | TLSv1.2      | ECDHE‑RSA‑AES128‑GCM‑SHA256 | Error                | HTTP/1.1     | *null*     |               *null* |  10524 |              0.078 | Error                       | text/html;%20charset=utf‑8 |         *null* |         *null* |       *null* |
....
