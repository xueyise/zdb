<table>
<tr>
<blockquote><th width='80'></th>
<th width='150'>Redis</th>
<th width='150'>SSDB</th>
</tr></blockquote>

<tr>
<blockquote><td>kv</td>
<td>get</td><td>get</td>
</tr>
<tr><td>set</td><td>set</td></tr>
<tr><td>del</td><td>del</td></tr>
<tr><td>incr/incrBy</td><td>incr</td></tr>
<tr><td>decr/decrBy</td><td>decr</td></tr>
<tr><td>getMultiple</td><td>multi_get</td></tr>
<tr><td>setMultiple</td><td>multi_set</td></tr>
<tr><td>del(multiple)</td><td>multi_del</td></tr>
<tr><td>keys</td><td>scan(for kv type only)</td></tr></blockquote>

<tr><td>-</td><td>-</td><td>-</td></tr>

<tr>
<blockquote><td>hashmap</td>
<td>hget</td><td>hget</td>
</tr>
<tr><td>hset</td><td>hset</td></tr>
<tr><td>hdel</td><td>hdel</td></tr>
<tr><td>hIncrBy</td><td>hincr</td></tr>
<tr><td>hDecrBy</td><td>hdecr</td></tr>
<tr><td>hKeys</td><td>hkeys</td></tr>
<tr><td>hVals</td><td>hscan</td></tr>
<tr><td>hMGet</td><td>multi_hget(in schedule)</td></tr>
<tr><td>hMSet</td><td>multi_hset(in schedule)</td></tr>
<tr><td>hLen</td><td>hsize(in schedule)</td></tr></blockquote>

<tr><td>-</td><td>-</td><td>-</td></tr>

<tr>
<blockquote><td>zset</td>
<td>zScore</td><td>zget</td>
</tr>
<tr><td>zAdd</td><td>zset</td></tr>
<tr><td>zRem</td><td>zdel</td></tr>
<tr><td>zRange</td><td></td></tr>
<tr><td>zRangeByScore</td><td>zscan</td></tr>
<tr><td>zIncrBy</td><td>zincr</td></tr>
<tr><td>zDecrBy</td><td>zdecr</td></tr>
<tr><td>zCount</td><td></td></tr>
<tr><td>zCard</td><td>zsize(in schedule)</td></tr>
</table>