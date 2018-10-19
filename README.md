# DroneEmployeeDocker

## Pre-install steps 

install 

* docker
* docker-compose

## Install steps

1. Clone repo

```bash
git clone https://github.com/muchosun/DroneEmployeeDocker.git
cd DroneEmployeeDocker
```
2. Make docker-compose

```bash
docker-compose up
```
3. Wait sync parity. (3-4 h)
4. Go to http://127.0.0.1:9000 and create new account for portainer.
5. Go to http://127.0.0.1:8888 for watch simualtion of flight.

#Note

In [docker-compose.yaml](docker-compose.yaml) you may change some parametrs:

```yaml
IPFS_API_ADDR: "http://172.16.238.100:5001" # if use local ipfs service insert "http://172.16.238.1:5001" and comment ipfs service
WEB3_API_ADDR: "http://parity:8545" # if use local parity service insert "http://gateway:8545" and comment parity service
```

Parity start with next parametrs:

```yaml
["--unsafe-expose", "--db-path", "/chain-data/", "-d", "/keys-store/" ,"--jsonrpc-interface", "all", "--jsonrpc-hosts", "all", "--ws-interface", "all", "--ws-origins", "all", "--fast-unlock" ,"--mode", "active", "--tracing", "off", "--pruning", "fast", "--db-compaction", "ssd", "--cache-size", "1024"]
```

ipfs daemon start with next parametrs:

```yaml
["--enable-pubsub-experiment"]
```
