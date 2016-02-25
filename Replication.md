SSDB uses two LevelDB databases, one is `data_db`, and the other is `meta_db`.

In `data_db` stores the real data, and `meta_db` stores SyncLogs.

LevelDB internally assigns auto increment sequence numbers to every write to the database, SSDB stores these writes(Puts, Deletes) persistently in a `meta_db`, but only keys and operate types(as SyncLog) and saved, not values.

Once a Slave connected with `sync`(sync next\_seq) command, the Master check if `next_seq` is in meta\_db, if not, the Master dump the full `data` to the Slave. At the mean time, evry write from client to the Master will be forwarded to all slaves.

Since every SyncLog has a sequnce number, a slave reconnected after network failure won't need a full dump, but only need SyncLogs from `next_seq`.


```
if(last_seq < change_log.min_seq){
    change_log.read_current();
    iterate from begin
}else{
    change_log.read_from(last_seq + 1);
    iterate from last_key
}

// dump
foreach(iterate as key=>value){
    // sync partially
    foreach(change_log as write){
        if(write.key < last_key){
            sync(write);
            last_seq = write.seq;
        }
    }
    sync(key, value);
    last_key = key;
}

// sync
foreach(change_log as write){
    sync(write);
    last_seq = write.seq;
}
```