# Introduction #

zRangeByScore is one of the most powerfull command in Redis, it is used in zset pagination, like 'list messages in by inbox'.

SSDB provides zscan, which is similar to zRangeByScore.

# Details #

Redis:

```
zRangeByScore(name, score_start, score_end, options);
```

SSDB:

```
zscan(name, key_start, score_start, score_end, limit);
```

The `key_start` parameter makes it possible to distinguish items with same score.