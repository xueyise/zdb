**A comparison with the Redis server is available at: http://www.ideawu.com/ssdb/**

Benchmarks was taken on:

  * Linode 512
  * Ubuntu 8.04 LTS

```
ssdb-benchmark.
Copyright (c) 2012 ideawu.com

preparing 10000 request(s)...
making 10 connection(s) to server...

======= set =======
qps: 13639, time: 0.733 s

======= get =======
qps: 19944, time: 0.501 s

======= scan =======
qps: 18515, time: 0.540 s

======= del =======
qps: 21256, time: 0.470 s

======= zset =======
qps: 14894, time: 0.671 s

======= zget =======
qps: 19049, time: 0.525 s

======= zscan =======
qps: 8271, time: 1.209 s

======= zdel =======
qps: 15641, time: 0.639 s
```