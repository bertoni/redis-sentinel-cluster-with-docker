# Redis Commands

See the infomation about replication
```
INFO REPLICATION
```

Storage "xpto" with key "project"
```
SET project xpto
```

Storage "really beautiful" with key "project" if this key doesn't exist
```
SETNX project "really beautiful"
```

Recover the value of "project" key
```
GET project
```

Remove the "project" key
```
DET project
```

Set TTL of "project" key for 30 seconds
```
EXPIRE project 30
```

Show how time of TTL some key still has (-2 if key doen't exist, -1 if key doesn't expire)
```
TTL project
```

### LISTS - A List is a sequence of ordered elements.

RPUSH inserts a new element at the end of the List (at the tail)
```
RPUSH engineers "Alice"
RPUSH engineers "Bob"
RPUSH engineers "Carmen"
```

LRANGE (key start stop) show the values inside a list (you can use stop with -1 to see all elements)
```
LRANGE engineers 0 100
```

LPUSH behaves the same as RPUSH except that it inserts the element at the front of the List (at the header)
```
LPUSH engineers "Daniel"
LPUSH engineers "Jack" "Francis"
```

LLEN show the length of a List
```
LLEN engineers
```

LPOP removes and returns the first element of the List
```
LPOP engineers
```

RPOP removes and returns the last element of the List
```
RPOP engineers
```

### SETS - Set is similar to a List except that it doesn't keep any specific order for its elements and each element must be unique.

SADD adds the specified members to the key
```
SADD languages "english"
SADD languages "spanish"
SADD languages "french"
SADD languages "chinese" "japanese" "german"
```

SREM remove members from a set
```
SREM languages "german"
SREM languages "english" "french"
```

SISMEMBER verify that a member is part of a set
```
SISMEMBER languages "spanish"
```

SMEMBERS show all the members that exist in a set
```
SMEMBERS languages
```

SUNION combine sets into one
```
SUNION languages ancient-languages
```

### HASHES - Hash is a data structure that maps a string key with field-value pairs.

HSET sets field in the Hash to value. If key does not exist, a new key storing a hash is created. If field already exists in the hash, it is overwritten.
```
HSET computer name "MacBook Pro"
HSET computer year 2015
HSET computer disk 512
HSET computer ram 16
HSET notebook name "Lenovo Thinkpad" year 2017 disk 1024 ram 32
```

HGET returns the value associated with field in a Hash
```
HGET computer year
```

HGETALL get all the fields with their values from the hash
```
HGETALL computer
```

HMGET get specific fields in the hash
```
HMGET computer disk ram
```


## Sentinel commands

For use this commands its necessary connect to a sentinel with telnet:
```
telnet 10.15.0.21 26379
```

See the data about master elected by sentinel
```
SENTINEL get-master-addr-by-name mymaster
```

Check how status of quorum in the cluster
```
SENTINEL ckquorum mymaster
```

Force the failover in the cluster
```
SENTINEL failover mymaster
```
