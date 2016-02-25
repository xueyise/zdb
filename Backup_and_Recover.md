ssdb-dump is a programm to backup a SSDB instance, it's located in SSDB\_PATH/tools.

# Usage #

```
Usage:
    ssdb-dump ip port output_folder

Options:
    ip - ssdb server ip address
    port - ssdb server port number
    output_folder - local backup folder that will be created
```

# Examples #

```
./tools/ssdb-dump 127.0.0.1 8888 backup_dir
```

A copy of SSDB instance(the leveldb database) will be saved in a new created directory `backup_dir`.

# Recover #

Transfer the directory `backup_dir` to the server on which ssdb-server runs, then edit ssdb.conf to use `backup_dir`, restart ssdb-server.