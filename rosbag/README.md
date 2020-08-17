## Publicly downloadable sample data

##### Source 1: ROS.org
http://wiki.ros.org/rosbag/Tutorials/reading%20msgs%20from%20a%20bag%20file
```shell script
wget https://open-source-webviz-ui.s3.amazonaws.com/demo.bag         # 696MB 
```

##### Source 2: MIT stata center data set
https://projects.csail.mit.edu/stata/downloads.php

```shell script
wget http://infinity.csail.mit.edu/data/2011/2011-04-06-07-04-17.bag # 349MB
wget http://infinity.csail.mit.edu/data/2011/2011-04-11-07-34-27.bag # 596MB
wget http://infinity.csail.mit.edu/data/2011/2011-04-15-06-16-49.bag # 606MB
wget http://infinity.csail.mit.edu/data/2011/2011-04-22-06-22-12.bag # 534MB
wget http://infinity.csail.mit.edu/data/2011/2011-04-22-06-52-29.bag # 637MB
wget http://infinity.csail.mit.edu/data/2011/2011-04-29-06-16-08.bag # 791MB
```

##### Source 3: Cartographer ROS Integration
https://google-cartographer-ros.readthedocs.io/en/latest/data.html
```shell script
wget https://storage.googleapis.com/cartographer-public-data/bags/backpack_3d/b3-2016-02-02-13-32-01.bag # 349MB
wget https://storage.googleapis.com/cartographer-public-data/bags/toru/hallway_localization.bag          #  40MB
wget https://storage.googleapis.com/cartographer-public-data/bags/toru/hallway_return.bag                # 102MB
wget https://storage.googleapis.com/cartographer-public-data/bags/mir/landmarks_demo_uncalibrated.bag    #  41MB
```


## Queries

### ./query_single_bag_metainfo.sx
```jsx
@bags = LIST('file:/data/pub_rosbag/demo.bag');

ROSBAG_META(src:@bags)
```
1 bag, 696MB data, 4 CPU Cores - 0.010 seconds

| uri                            |    length | conn | startTime                       | endTime                         | chunks | messages | chunksLength | topic                          | type                             | md5sum                           | messageDefinition       |
|--------------------------------|----------:|-----:|---------------------------------|---------------------------------|-------:|---------:|-------------:|--------------------------------|----------------------------------|----------------------------------|-------------------------|
| file:/data/pub_rosbag/demo.bag | 729967395 |    0 | `2017‑03‑22 04:37:58.001 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    451 |     1986 |    539779984 | /tf                            | tf2_msgs/TFMessage               | 94810edda583a504dfda3829e70d7eec | <2129 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |    1 | `2017‑03‑22 04:37:58.001 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    401 |      600 |    477012565 | /image_raw                     | sensor_msgs/Image                | 060021388200f6f0f447d0fcd9c64743 | <2049 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |    2 | `2017‑03‑22 04:37:58.001 +0200` | `2017‑03‑22 04:38:17.940 +0200` |    200 |      200 |    188232928 | /velodyne_packets              | velodyne_msgs/VelodyneScan       | 50804fc9533a0e579e6322c04ae70566 | <1068 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |    3 | `2017‑03‑22 04:37:58.021 +0200` | `2017‑03‑22 04:38:17.940 +0200` |    200 |      200 |    254817225 | /velodyne_points               | sensor_msgs/PointCloud2          | 1158d486dd51d683ce2f1be655c3c181 | <2260 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |    4 | `2017‑03‑22 04:37:58.032 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    385 |      400 |    460946134 | /radar/points                  | sensor_msgs/PointCloud2          | 1158d486dd51d683ce2f1be655c3c181 | <2260 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |    5 | `2017‑03‑22 04:37:58.032 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    385 |      400 |    460946134 | /radar/range                   | sensor_msgs/Range                | c005c34273dc426c67a020a87bc24148 | <2713 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |    6 | `2017‑03‑22 04:37:58.032 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    385 |      400 |    460946134 | /radar/tracks                  | radar_driver/RadarTracks         | 6a2de2f790cb8bb0e149d45d297462f8 | <982 bytes MD text...>  |
| file:/data/pub_rosbag/demo.bag | 729967395 |    7 | `2017‑03‑22 04:37:58.032 +0200` | `2017‑03‑22 04:38:17.706 +0200` |     40 |       40 |     57579000 | /diagnostics_toplevel_state    | diagnostic_msgs/DiagnosticStatus | d0ce08bc6e5ba34c7754f563a9cabaf1 | <631 bytes MD text...>  |
| file:/data/pub_rosbag/demo.bag | 729967395 |    8 | `2017‑03‑22 04:37:58.032 +0200` | `2017‑03‑22 04:38:17.706 +0200` |     40 |       40 |     57086089 | /diagnostics_agg               | diagnostic_msgs/DiagnosticArray  | 60810da900de1dd6ddd437c3503511da | <1617 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |    9 | `2017‑03‑22 04:37:58.082 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    136 |      136 |    185376998 | /obs1/gps/time                 | sensor_msgs/TimeReference        | fded64a0265108ba86c3d38fb11c0c16 | <1007 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |   10 | `2017‑03‑22 04:37:58.082 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    192 |      192 |    261405337 | /gps/time                      | sensor_msgs/TimeReference        | fded64a0265108ba86c3d38fb11c0c16 | <1007 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |   11 | `2017‑03‑22 04:37:58.082 +0200` | `2017‑03‑22 04:38:17.806 +0200` |    146 |      146 |    198970902 | /gps/fix                       | sensor_msgs/NavSatFix            | 2d3a8cd499b9b4a0249fb98fd05cfa48 | <3147 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |   12 | `2017‑03‑22 04:37:58.082 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    200 |      200 |    194559790 | /obs1/gps/rtkfix               | nav_msgs/Odometry                | cd5e73d190d741a2f92e81eda573aca7 | <3310 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |   13 | `2017‑03‑22 04:37:58.082 +0200` | `2017‑03‑22 04:38:17.996 +0200` |    200 |      200 |    195063134 | /gps/rtkfix                    | nav_msgs/Odometry                | cd5e73d190d741a2f92e81eda573aca7 | <3310 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |   14 | `2017‑03‑22 04:37:58.474 +0200` | `2017‑03‑22 04:38:17.906 +0200` |     80 |      140 |     88112285 | /diagnostics                   | diagnostic_msgs/DiagnosticArray  | 60810da900de1dd6ddd437c3503511da | <1617 bytes MD text...> |
| file:/data/pub_rosbag/demo.bag | 729967395 |   15 | `2017‑03‑22 04:37:58.828 +0200` | `2017‑03‑22 04:38:17.940 +0200` |     59 |       80 |     74429205 | /velodyne_nodelet_manager/bond | bond/Status                      | eacc84bf5d65b6777d4c50f463dfb9c8 | <951 bytes MD text...>  |
| file:/data/pub_rosbag/demo.bag | 729967395 |   16 | `2017‑03‑22 04:37:59.774 +0200` | `2017‑03‑22 04:38:17.806 +0200` |     30 |       30 |     35680235 | /obs1/gps/fix                  | sensor_msgs/NavSatFix            | 2d3a8cd499b9b4a0249fb98fd05cfa48 | <3147 bytes MD text...> |

### ./query_multiple_bags_metainfo.sx
```jsx
@bags = LIST('file:/data/pub_rosbag/*.bag');

ROSBAG_META(src:@bags)
| select(uri, min(startTime), max(endTime), sum_long(messages))
| group(uri)
| sort(max_endTime)
```
1 bag, 696MB data, 4 CPU Cores - 0.024 seconds

| uri                                                   | min_startTime                   | max_endTime                     | sum_long_messages |
|-------------------------------------------------------|---------------------------------|---------------------------------|------------------:|
| file:/data/pub_rosbag/2011‑04‑06‑07‑04‑17.bag         | `2011‑04‑06 17:04:17.702 +0300` | `2011‑04‑06 17:09:41.914 +0300` |            105032 |
| file:/data/pub_rosbag/2011‑04‑11‑07‑34‑27.bag         | `2011‑04‑11 17:34:27.495 +0300` | `2011‑04‑11 17:54:14.803 +0300` |            380172 |
| file:/data/pub_rosbag/2011‑04‑15‑06‑16‑49.bag         | `2011‑04‑15 16:16:49.852 +0300` | `2011‑04‑15 16:36:40.989 +0300` |            383594 |
| file:/data/pub_rosbag/2011‑04‑22‑06‑22‑12.bag         | `2011‑04‑22 16:22:12.814 +0300` | `2011‑04‑22 16:42:12.410 +0300` |            361875 |
| file:/data/pub_rosbag/2011‑04‑22‑06‑52‑29.bag         | `2011‑04‑22 16:52:29.518 +0300` | `2011‑04‑22 17:16:25.220 +0300` |            432932 |
| file:/data/pub_rosbag/2011‑04‑29‑06‑16‑08.bag         | `2011‑04‑29 16:16:08.373 +0300` | `2011‑04‑29 16:42:10.391 +0300` |            502470 |
| file:/data/pub_rosbag/b3‑2016‑02‑02‑13‑32‑01.bag      | `2016‑02‑02 15:32:01.613 +0200` | `2016‑02‑02 15:32:48.856 +0200` |            154207 |
| file:/data/pub_rosbag/demo.bag                        | `2017‑03‑22 04:37:58.001 +0200` | `2017‑03‑22 04:38:17.996 +0200` |              5390 |
| file:/data/pub_rosbag/hallway_return.bag              | `2017‑12‑18 15:03:12.517 +0200` | `2017‑12‑18 15:09:03.480 +0200` |            201263 |
| file:/data/pub_rosbag/hallway_localization.bag        | `2018‑02‑19 17:56:41.703 +0200` | `2018‑02‑19 17:58:59.443 +0200` |             79024 |
| file:/data/pub_rosbag/landmarks_demo_uncalibrated.bag | `2018‑07‑26 18:21:31.723 +0300` | `2018‑07‑26 18:27:31.661 +0300` |             74079 |

### ./query_all_topics.sx
```jsx
@list     = LIST('file:/data/pub_rosbag/demo.bag');
@messages = ROSBAG(src:@list);

@messages
| select(_file_name, *)
| limit(1000)
```
1 bag, 696MB data, 1 CPU Cores - 0.686 seconds

| _file_name | time                                  | topic                       | add                                                                                                     |
|------------|---------------------------------------|-----------------------------|---------------------------------------------------------------------------------------------------------|
| demo.bag   | `2017‑03‑22 04:37:58.062303409 +0200` | /tf                         | {"transforms":[{"header":{"seq":0,"stamp":"2017‑03‑22 04:37:58.072189535 +0200","frame_id":"base_lin... |
| demo.bag   | `2017‑03‑22 04:37:58.066884454 +0200` | /diagnostics_toplevel_state | {"level":0,"name":"toplevel_state","message":"","hardware_id":"","values":[]}...                        |
| demo.bag   | `2017‑03‑22 04:37:58.067329189 +0200` | /diagnostics_agg            | {"header":{"seq":1839,"stamp":"2017‑03‑22 04:37:58.040781979 +0200","frame_id":""},"status":[{"level... |
| demo.bag   | `2017‑03‑22 04:37:58.072357316 +0200` | /tf                         | {"transforms":[{"header":{"seq":0,"stamp":"2017‑03‑22 04:37:58.082272317 +0200","frame_id":"base_lin... |
| demo.bag   | `2017‑03‑22 04:37:58.073280873 +0200` | /image_raw                  | {"header":{"seq":99048,"stamp":"2017‑03‑22 04:37:58.072573979 +0200","frame_id":"camera"},"height":5... |
| demo.bag   | `2017‑03‑22 04:37:58.082416132 +0200` | /tf                         | {"transforms":[{"header":{"seq":0,"stamp":"2017‑03‑22 04:37:58.092359147 +0200","frame_id":"base_lin... |
| demo.bag   | `2017‑03‑22 04:37:58.089146483 +0200` | /obs1/gps/time              | {"header":{"seq":13491,"stamp":"2017‑03‑22 04:37:58.063058521 +0200","frame_id":"gps"},"time_ref":"1... |
| demo.bag   | `2017‑03‑22 04:37:58.091118854 +0200` | /gps/time                   | {"header":{"seq":32476,"stamp":"2017‑03‑22 04:37:58.091023147 +0200","frame_id":"gps"},"time_ref":"1... |
| demo.bag   | `2017‑03‑22 04:37:58.092496871 +0200` | /tf                         | {"transforms":[{"header":{"seq":0,"stamp":"2017‑03‑22 04:37:58.102448914 +0200","frame_id":"base_lin... |
| demo.bag   | `2017‑03‑22 04:37:58.094034595 +0200` | /gps/fix                    | {"header":{"seq":24204,"stamp":"2017‑03‑22 04:37:58.093991776 +0200","frame_id":"gps"},"status":{"st... |
| demo.bag   | `2017‑03‑22 04:37:58.095426184 +0200` | /radar/points               | {"header":{"seq":19446,"stamp":"2017‑03‑22 04:37:58.095235109 +0200","frame_id":"radar"},"height":1,... |
| demo.bag   | `2017‑03‑22 04:37:58.095470113 +0200` | /radar/range                | {"header":{"seq":19446,"stamp":"2017‑03‑22 04:37:58.095386028 +0200","frame_id":"radar"},"radiation_... |
| demo.bag   | `2017‑03‑22 04:37:58.095600888 +0200` | /radar/tracks               | {"header":{"seq":19447,"stamp":"2017‑03‑22 04:37:58.095324993 +0200","frame_id":""},"tracks":[{"stat... |

### ./stats_per_1000ms.sx
```jsx
@list     = LIST('file:/data/pub_rosbag/demo.bag');
@messages = ROSBAG(src:@list);

@messages
| select(time[1000ms], events:count(*), bytes:long(sum(dataLen)))
| group(@1)
```
1 bag, 696MB data, 1 CPU Cores - 0.289 seconds

| time_submod                     | events |    bytes |
|---------------------------------|-------:|---------:|
| `2017‑03‑22 04:37:58.000 +0200` |    267 | 36044380 |
| `2017‑03‑22 04:37:59.000 +0200` |    269 | 36231325 |
| `2017‑03‑22 04:38:00.000 +0200` |    264 | 36392149 |
| `2017‑03‑22 04:38:01.000 +0200` |    271 | 36436878 |
| `2017‑03‑22 04:38:02.000 +0200` |    270 | 36494606 |
| `2017‑03‑22 04:38:03.000 +0200` |    272 | 36490441 |
| `2017‑03‑22 04:38:04.000 +0200` |    268 | 36521889 |
| `2017‑03‑22 04:38:05.000 +0200` |    272 | 36491561 |
| `2017‑03‑22 04:38:06.000 +0200` |    272 | 36516279 |
| `2017‑03‑22 04:38:07.000 +0200` |    268 | 36588903 |

### ./query_single_topic.sx
```jsx
@list     = LIST('file:/data/pub_rosbag/demo.bag');
@messages = ROSBAG(src:@list);

@messages
| filter(topic = "/gps/fix")
| select(time, geo(value[latitude], value[longitude]), value[status][status])
```
1 bag, 696MB data, 1 CPU Cores - 0.285 seconds

| time                                  | geo                 | status |
|---------------------------------------|---------------------|--------|
| `2017‑03‑22 04:37:58.094034595 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:58.169991489 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:58.370770352 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:58.469751795 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:58.570684635 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:58.669613884 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:58.769493181 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:59.170101299 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:59.269056829 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:59.369957951 +0200` | 37.40086,‑122.10782 | 0      |
| `2017‑03‑22 04:37:59.498879562 +0200` | 37.40086,‑122.10782 | 0      |

### ./correlate_2_topics.sx
```jsx
@list     = LIST('file:/data/pub_rosbag/demo.bag');
@messages = ROSBAG(src:@list);

@messages
| filter(topic IN ("/gps/fix", "/obs1/gps/fix"))
| select(time,
         gps_fix:keep(if(topic="/gps/fix", value)), 
         obs1_gps_fix:keep(if(topic="/obs1/gps/fix", value))
)
| filter(obs1_gps_fix is not null)
| select(time, 
         pos:geo(gps_fix[latitude], gps_fix[longitude]),
         obs_pos:geo(obs1_gps_fix[latitude], obs1_gps_fix[longitude])
)
| select(*, distance_to_obs_meters:1000*DISTANCE(pos, obs_pos))
| sort(distance_to_obs_meters DESC)
```
1 bag, 696MB data, 1 CPU Cores - 0.293 seconds

| time                                  | pos                   | obs_pos               | distance_to_obs_meters |
|---------------------------------------|-----------------------|-----------------------|-----------------------:|
| `2017‑03‑22 04:38:17.668958261 +0200` | 37.400692,‑122.108215 | 37.400803,‑122.108116 |     15.102127227665406 |
| `2017‑03‑22 04:38:17.769384804 +0200` | 37.400692,‑122.108215 | 37.400803,‑122.108116 |     15.102127227665406 |
| `2017‑03‑22 04:38:17.569468226 +0200` | 37.400696,‑122.108215 | 37.400803,‑122.108116 |     14.758677148983786 |
| `2017‑03‑22 04:38:17.368694539 +0200` | 37.4007,‑122.10821    | 37.400803,‑122.108116 |     14.020271020617882 |
| `2017‑03‑22 04:38:17.481553289 +0200` | 37.4007,‑122.10821    | 37.400803,‑122.108116 |     14.020271020617882 |
| `2017‑03‑22 04:38:14.967769056 +0200` | 37.400764,‑122.108154 | 37.400867,‑122.10807  |     13.642638155869488 |
| `2017‑03‑22 04:38:17.169836880 +0200` | 37.400707,‑122.10821  | 37.400803,‑122.108116 |     13.336260854568984 |
| `2017‑03‑22 04:38:14.768010705 +0200` | 37.40077,‑122.108154  | 37.400867,‑122.10807  |      13.28855067389353 |
| `2017‑03‑22 04:38:14.867841279 +0200` | 37.40077,‑122.108154  | 37.400867,‑122.10807  |      13.28855067389353 |
| `2017‑03‑22 04:38:17.090928203 +0200` | 37.400707,‑122.1082   | 37.400803,‑122.108116 |     12.938683322595706 |
| `2017‑03‑22 04:38:16.969042424 +0200` | 37.40071,‑122.1082    | 37.400803,‑122.108116 |      12.59338028277549 |

### ./query_topic_stats.sx
```jsx
@list     = LIST('file:/data/pub_rosbag/demo.bag');
@messages = ROSBAG(src:@list);

@messages
| select(topic, 
         count(*), 
         min(dataLen), 
         max(dataLen), 
         avg_data_len:long(avg(dataLen)), 
         total_data_len:long(sum(dataLen))
)
| group(topic)
```
1 bag, 696MB data, 1 CPU Cores - 0.285 seconds

| topic                          | count | min_dataLen | max_dataLen | avg_data_len | total_data_len |
|--------------------------------|------:|------------:|------------:|-------------:|---------------:|
| /diagnostics                   |   140 |         336 |        1221 |          644 |          90295 |
| /diagnostics_agg               |    40 |        2114 |        2990 |         2557 |         102295 |
| /diagnostics_toplevel_state    |    40 |          31 |          31 |           31 |           1240 |
| /gps/fix                       |   146 |         119 |         119 |          119 |          17374 |
| /gps/rtkfix                    |   200 |         703 |         703 |          703 |         140600 |
| /gps/time                      |   192 |          34 |          34 |           34 |           6528 |
| /image_raw                     |   600 |      716854 |      716854 |       716854 |      430112400 |
| /obs1/gps/fix                  |    30 |         119 |         119 |          119 |           3570 |
| /obs1/gps/rtkfix               |   200 |         703 |         703 |          703 |         140600 |
| /obs1/gps/time                 |   136 |          34 |          34 |           34 |           4624 |
| /radar/points                  |   400 |         173 |         497 |          306 |         122600 |
| /radar/range                   |   400 |          38 |          38 |           38 |          15200 |
| /radar/tracks                  |   400 |         307 |        1414 |          763 |         305250 |
| /tf                            |  1986 |          94 |          94 |           94 |         186684 |
| /velodyne_nodelet_manager/bond |    80 |         120 |         121 |          120 |           9640 |
| /velodyne_packets              |   200 |      219762 |      219762 |       219762 |       43952400 |
| /velodyne_points               |   200 |     1223683 |     1286979 |      1270252 |      254050424 |

### ./query_values_before_crash.sx
```jsx
$file='file:/data/pub_rosbag/demo.bag';
$crash_time=tnano("2017-03-22 04:38:00.068296671 +0200");

ROSBAG(src:$file, last_topic_time:$crash_time)
| select(topic, last(time), last(value))
| group(topic)
| select(topic, last_time, nanos_from_crash:$crash_time-last_time, last_value)
```
1 bag, 696MB data, 1 CPU Cores - 0.445 seconds

| topic                          | last_time                             | nanos_from_crash | last_value                                                                                                                       |
|--------------------------------|---------------------------------------|-----------------:|----------------------------------------------------------------------------------------------------------------------------------|
| /diagnostics                   | `2017‑03‑22 04:37:59.883427817 +0200` |        184868854 | {"header":{"seq":5520,"stamp":"2017‑03‑22 04:37:59.854942204 +0200","frame_id":""},"status":[{"level":0,"name":"piksi_rtk_diag:  |
| /diagnostics_agg               | `2017‑03‑22 04:37:59.658565210 +0200` |        409731461 | {"header":{"seq":3571,"stamp":"2017‑03‑22 04:37:59.658464829 +0200","frame_id":""},"status":[{"level":0,"name":"/GPS","message": |
| /diagnostics_toplevel_state    | `2017‑03‑22 04:38:00.068296671 +0200` |                0 | {"level":0,"name":"toplevel_state","message":"","hardware_id":"","values":[]}                                                    |
| /gps/fix                       | `2017‑03‑22 04:37:59.969394630 +0200` |         98902041 | {"header":{"seq":24219,"stamp":"2017‑03‑22 04:37:59.969321422 +0200","frame_id":"gps"},"status":{"status":0,"service":1},"latitu |
| /gps/rtkfix                    | `2017‑03‑22 04:37:59.984403758 +0200` |         83892913 | {"header":{"seq":35712,"stamp":"2017‑03‑22 04:37:59.984324602 +0200","frame_id":"gps"},"child_frame_id":"","pose":{"pose":{"posi |
| /gps/time                      | `2017‑03‑22 04:37:59.966381924 +0200` |        101914747 | {"header":{"seq":32494,"stamp":"2017‑03‑22 04:37:59.966324399 +0200","frame_id":"gps"},"time_ref":"1978‑07‑08 01:18:20.000000000 |
| /image_raw                     | `2017‑03‑22 04:38:00.040130232 +0200` |         28166439 | {"header":{"seq":99107,"stamp":"2017‑03‑22 04:38:00.039372812 +0200","frame_id":"camera"},"height":512,"width":1400,"encoding":" |
| /obs1/gps/fix                  | `2017‑03‑22 04:37:59.784405894 +0200` |        283890777 | {"header":{"seq":3999,"stamp":"2017‑03‑22 04:37:59.743694124 +0200","frame_id":"gps"},"status":{"status":0,"service":1},"latitud |
| /obs1/gps/rtkfix               | `2017‑03‑22 04:37:59.983891846 +0200` |         84404825 | {"header":{"seq":18409,"stamp":"2017‑03‑22 04:37:59.957637081 +0200","frame_id":"gps"},"child_frame_id":"","pose":{"pose":{"posi |
| /obs1/gps/time                 | `2017‑03‑22 04:37:59.964665913 +0200` |        103630758 | {"header":{"seq":13501,"stamp":"2017‑03‑22 04:37:59.938574843 +0200","frame_id":"gps"},"time_ref":"1978‑07‑08 01:18:20.000000000 |
| /radar/points                  | `2017‑03‑22 04:38:00.045561152 +0200` |         22735519 | {"header":{"seq":19485,"stamp":"2017‑03‑22 04:38:00.045351982 +0200","frame_id":"radar"},"height":1,"width":18,"fields":[{"name" |
| /radar/range                   | `2017‑03‑22 04:38:00.045702837 +0200` |         22593834 | {"header":{"seq":19485,"stamp":"2017‑03‑22 04:38:00.045510053 +0200","frame_id":"radar"},"radiation_type":1,"field_of_view":0.03 |
| /radar/tracks                  | `2017‑03‑22 04:38:00.045692051 +0200` |         22604620 | {"header":{"seq":19486,"stamp":"2017‑03‑22 04:38:00.045447111 +0200","frame_id":""},"tracks":[{"status":3,"number":1,"range":47. |
| /tf                            | `2017‑03‑22 04:38:00.066752921 +0200` |          1543750 | {"transforms":[{"header":{"seq":0,"stamp":"2017‑03‑22 04:38:00.076665042 +0200","frame_id":"base_link"},"child_frame_id":"radar" |
| /velodyne_nodelet_manager/bond | `2017‑03‑22 04:37:59.936875568 +0200` |        131421103 | {"header":{"seq":3303,"stamp":"2017‑03‑22 04:37:59.936821237 +0200","frame_id":""},"id":"/cloud_nodelet_5795a91f‑b289‑4c6a‑b9bc‑ |
| /velodyne_packets              | `2017‑03‑22 04:38:00.022560202 +0200` |         45736469 | {"header":{"seq":9729,"stamp":"2017‑03‑22 04:38:00.022079468 +0200","frame_id":"velodyne"},"packets":[{"stamp":"2017‑03‑22 04:37 |
| /velodyne_points               | `2017‑03‑22 04:38:00.025199232 +0200` |         43097439 | {"header":{"seq":9727,"stamp":"2017‑03‑22 04:38:00.022079000 +0200","frame_id":"velodyne"},"height":1,"width":39322,"fields":[{" |

### ./access_file_metainfo.sx
```jsx
@list     = LIST('file:/data/pub_rosbag/2011-*.bag');
@messages = ROSBAG(src:@list);

@messages
| filter(topic = "/torso_lift_imu/data")
| filter(value[angular_velocity][x] between 0.15 and 0.17)
| select(_uri, time, value[angular_velocity])
```
6 bags, ~3.5GB data, 4 CPU Cores - 1.104 seconds

| _uri                                          | time                                  | angular_velocity                                                             |
|-----------------------------------------------|---------------------------------------|------------------------------------------------------------------------------|
| file:/data/pub_rosbag/2011‑04‑15‑06‑16‑49.bag | `2011‑04‑15 16:20:00.450996799 +0300` | {"x":0.15406547486782074,"y":‑0.10743137449026108,"z":0.14496155083179474}   |
| file:/data/pub_rosbag/2011‑04‑15‑06‑16‑49.bag | `2011‑04‑15 16:24:23.788199924 +0300` | {"x":0.15233242511749268,"y":‑0.09283081442117691,"z":‑0.03807494044303894}  |
| file:/data/pub_rosbag/2011‑04‑15‑06‑16‑49.bag | `2011‑04‑15 16:32:57.291497733 +0300` | {"x":0.16912458837032318,"y":‑0.19228829443454742,"z":0.2212289273738861}    |
| file:/data/pub_rosbag/2011‑04‑11‑07‑34‑27.bag | `2011‑04‑11 17:37:34.830696457 +0300` | {"x":0.15395653247833252,"y":‑0.11510616540908813,"z":‑0.12670426070690155}  |
| file:/data/pub_rosbag/2011‑04‑11‑07‑34‑27.bag | `2011‑04‑11 17:47:05.302208023 +0300` | {"x":0.1558019071817398,"y":‑0.02212025411427021,"z":‑0.002891015261411667}  |
| file:/data/pub_rosbag/2011‑04‑11‑07‑34‑27.bag | `2011‑04‑11 17:47:05.312222657 +0300` | {"x":0.16674400866031647,"y":‑0.05958309397101402,"z":‑0.023051902651786804} |
| file:/data/pub_rosbag/2011‑04‑11‑07‑34‑27.bag | `2011‑04‑11 17:47:36.350378235 +0300` | {"x":0.15285763144493103,"y":0.07952265441417694,"z":0.010994544252753258}   |
| file:/data/pub_rosbag/2011‑04‑22‑06‑22‑12.bag | `2011‑04‑22 16:23:20.118452508 +0300` | {"x":0.15171611309051514,"y":‑0.1905963271856308,"z":‑0.0030932959634810686} |
| file:/data/pub_rosbag/2011‑04‑29‑06‑16‑08.bag | `2011‑04‑29 16:37:00.966766819 +0300` | {"x":0.16868340969085693,"y":0.07906853407621384,"z":‑0.006509881466627121}  |
| file:/data/pub_rosbag/2011‑04‑22‑06‑52‑29.bag | `2011‑04‑22 17:01:31.301634294 +0300` | {"x":0.15385650098323822,"y":‑0.15661406517028809,"z":‑0.01914442516863346}  |
| file:/data/pub_rosbag/2011‑04‑22‑06‑52‑29.bag | `2011‑04‑22 17:09:18.587700900 +0300` | {"x":0.15947310626506805,"y":‑0.048629533499479294,"z":0.06307824701070786}  |
| file:/data/pub_rosbag/2011‑04‑22‑06‑52‑29.bag | `2011‑04‑22 17:15:47.587161476 +0300` | {"x":0.15869610011577606,"y":0.0020697591826319695,"z":0.10447122901678085}  |
| file:/data/pub_rosbag/2011‑04‑22‑06‑52‑29.bag | `2011‑04‑22 17:15:48.407226734 +0300` | {"x":0.1508227288722992,"y":‑0.018922995775938034,"z":0.23772069811820984}   |
| file:/data/pub_rosbag/2011‑04‑22‑06‑52‑29.bag | `2011‑04‑22 17:15:48.447214494 +0300` | {"x":0.168234184384346,"y":‑0.006069456227123737,"z":0.15741756558418274}    |
