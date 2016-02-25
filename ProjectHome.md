.
.
# <font color='#cccc33'>SSDB has been moved to <a href='https://github.com/ideawu/ssdb'>github</a>!</font> #

# <font color='#cccc33'><a href='https://github.com/ideawu/ssdb/archive/master.zip'>Download from new place!</a></font> #

# <font color='#cccc33'><a href='http://www.ideawu.net/blog/category/ssdb'>SSDB 中文文档和教程</a></font> #

# <font color='#cccc33'><a href='http://www.ideawu.com/ssdb/docs/zh_cn/php/'>SSDB PHP API 中文文档</a></font> #

.
.

---


SSDB, also known as zdb, is a fast key-value(key-string, key-zset, key-hashmap) persistent storage server, using Google LevelDB as storage engine.

# Features #

  * LevelDB client-server support, written in C/C++
  * Persistent key-value, key-zset, key-hashmap storage([Commands](Commands.md))
  * Client API supports including PHP, Python, Cpy
  * Online backup, fast recover
  * **Replication(master-slave), load balance**
  * _Future Features_
    * Distributed

# PHP client API example #

```
<?php
require_once('SSDB.php');
$ssdb = new SSDB('127.0.0.1', 8888);
$resp = $ssdb->set('key', '123');
$resp = $ssdb->get('key');
echo $resp->data; // output: 123
```

[More...](Documentation_PHP_API.md)

# Performance #

## SSDB vs Redis ##

![http://www.ideawu.com/ssdb/ssdb-vs-redis.png](http://www.ideawu.com/ssdb/ssdb-vs-redis.png)

[View full SSDB vs Redis benchmark charts...](http://www.ideawu.com/ssdb/)

```
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

See [Benchmark](Benchmark.md)

# Who's using SSDB? #

See [Users](Users.md)
