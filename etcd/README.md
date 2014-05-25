# kelseyhightower:demo

## Setting up a three node cluster

```
#!/bin/bash
export HOSTIP="10.0.1.15"

docker run -d -p "34001:4001" -p "37001:7001" -name machine1 \
-e ETCD_NAME="machine1" \
-e ETCD_ADDR="$HOSTIP:34001" \
-e ETCD_BIND_ADDR="0.0.0.0:4001" \
-e ETCD_PEER_ADDR="$HOSTIP:37001" \
-e ETCD_PEER_BIND_ADDR="0.0.0.0:7001" \
kelseyhightower/etcd:demo

docker run -d -p "34002:4001" -p "37002:7001" -name machine2 \
-e ETCD_NAME="machine2" \
-e ETCD_ADDR="$HOSTIP:34002" \
-e ETCD_BIND_ADDR="0.0.0.0:4001" \
-e ETCD_PEER_ADDR="$HOSTIP:37002" \
-e ETCD_PEER_BIND_ADDR="0.0.0.0:7001" \
-e ETCD_PEERS="$HOSTIP:37001" \
kelseyhightower/etcd:demo

docker run -d -p "34003:4001" -p "37003:7001" -name machine3 \
-e ETCD_NAME="machine3" \
-e ETCD_ADDR="$HOSTIP:34003" \
-e ETCD_BIND_ADDR="0.0.0.0:4001" \
-e ETCD_PEER_ADDR="$HOSTIP:37003" \
-e ETCD_PEER_BIND_ADDR="0.0.0.0:7001" \
-e ETCD_PEERS="$HOSTIP:37001" \
kelseyhightower/etcd:demo
```
