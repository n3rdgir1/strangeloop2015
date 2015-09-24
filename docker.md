# Docker

Slides: http://view.dckr.info/#1

vmstat 1 = give stats on the host vm and update every second

docker-compose load balancing!

```
rng1:
    build: rng
rng2:
    build: rng
rng3:
    build: rng

rng0:
    image: jpetazzo/hamba
    links:
      - rng1
      - rng2
      - rng3
    command: 80 rng1 80 rng2 80 rng3 80
    ports:
      - "8001:80"
```

## Ambassadors:

```
redis:
  image: jpetazzo/hamba
  command: 6379 54.173.44.21 32769
```
  
* work as local load balancers, saving a hop
* negative impact on load balancer fairness
	* each node will load balance their output, and has no idea what the other ambassadors are doing (usually not a huge problem)

## Checking on network traffic on a running container:

```
docker run --net container:myredis -ti alpine
```

alpine: super slim linux container

