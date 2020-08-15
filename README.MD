# Create Redis/Sentinel cluster with Docker

The docker-compose.yml will launch 9 redis (1 master and 8 slaves) and 9 sentinels.

The quorum configured was 3, that accept lose until 4 nodes (containers in this case) of redis/sentinel (I assume that the installation of sentinel will be sidecar with redis).

### commands

There is a [page with the main commands](COMMANDS.MD) of redis/sentinel that you will use to interact with them.

### References
- https://medium.com/@amila922/redis-sentinel-high-availability-everything-you-need-to-know-from-dev-to-prod-complete-guide-deb198e70ea6
- https://medium.com/@gustavo.leitao/criando-um-cluster-com-redis-com-docker-9e2a1bc78d84
- https://medium.com/@mustafa.ileri/redis-clustering-with-redis-sentinel-on-docker-1090ab876f97
- https://hub.docker.com/_/redis
- https://www.youtube.com/watch?v=-a07Ief51H4&t=2388s
- https://redis.io/topics/sentinel
- https://redis.io/commands/cluster-set-config-epoch
- http://www.obsis.unb.br/gitlab/help/administration/high_availability/redis.md
- https://github.com/redis/redis/issues/1972
