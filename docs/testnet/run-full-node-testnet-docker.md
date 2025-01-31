# How to join the Secret Network as a full node on mainnet

This document details how to join the Secret Network `testnet` as a validator.

## Requirements

- Ubuntu/Debian host (with ZFS or LVM to be able to add more storage easily)
- A public IP address
- Open ports `TCP 26656 & 26657` _Note: If you're behind a router or firewall then you'll need to port forward on the network device._
- Reading https://docs.tendermint.com/master/tendermint-core/running-in-production.html
- RPC address of an already active node. You can use `bootstrap.secrettestnet.io:26657`, or any other node that exposes RPC services.
- Account with at least 1 SCRT

### Minimum requirements

- 1GB RAM
- 150GB SSD for Prune Everyting, or default pruining. 1TB premium SSD for Archive nodes.
- 1 dedicated core of any Intel Xeon CPU with SGX through SPS.

### Recommended requirements

- 4GB RAM
- 256GB SSD for Prune Everyting, or default pruining. 1TB premium SSD for Archive nodes.
- 2 dedicated core of any Intel Xeon CPU with SGX through SPS.
- Known Working CPUs (E-2276G, E-2278G, E-2286G, E-2288G) Non Xeon CPUs are reported to not get updated often enough to be compliant.
- Motherboard with support for SGX in the BIOS

Refer to https://ark.intel.com/content/www/us/en/ark.html#@Processors if unsure if your processor supports SGX.

## Prerequisites

### 1. Install docker and docker-compose

For Ubuntu 18.04:

```shell script
sudo ./setup_host.sh
```

## Installation

### 1. Download the good stuff
```shell script
wget www.file.com
```

### 2. Extract
```shell script
tar -xvf this-bundle.tar 
```


### 3. Run
```shell script
./run.sh
```

### 4. Check that the node is running

```shell script
docker logs -f secretnetwork_node_1
```

### 5. Configuration files

Mapping of the secretd/secretcli configuration files are located in
```shell script
- /home/bob/.secretd:/tmp/.secretd
- /tmp/secretcli:/root/.secretcli
```

And are set in `docker-compose.testnet.node.yaml`. Feel free to modify these to match your settings
