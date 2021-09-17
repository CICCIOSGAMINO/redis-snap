redis-snap
==========
[TOC]

Redis snap. Build the snap for Redis.

```bash
# clone the repo and remove git stuff
git clone --depth=1 https://github.com/CICCIOSGAMINO/redis-snap.git . && rm -rf ./.git

# change the redis version you want build
vim snap/snapcraft.yaml  # source-tag: '6.2.5'

# change the redis.config (configuration file for redis)
vim redis/config/redis.conf

# create the redis snap
snapcraft --debug

# install the snap from local
snap install --devmode redis_6.2.5_amd64.snap

# get info about the snap (description, commands etc.)
snap info redis

# run redis-server
redis.redis-server

# create an alias (if you need one)
sudo snap alias redis.redis-server redis-server
# check if an aliase is defined
snap aliases redis
> Command             Alias         Notes
  redis.redis-server  redis-server  manual
# remove alias
snap unalias redis
```

# Redis Configuration
The configuration file **redis.conf** is saved in $SNAP_COMMON path, as usual in ubuntu installation you can fin the file in /var/snap/redis-snap/common/redis.conf path. Here you can modify the **redis.conf** file and restart the redis server.

