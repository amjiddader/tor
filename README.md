# TOR , DARKWEB

This repo contains personal and public repos/apps/softwares that are useful for TOR. \
Warning: I do not endorse anyone to use Darkweb as it is very serious and dengerous...

## 1 TOR DNS RESOLVER 
Make sure you create a newtwork if you want to use another doecker on same system and want to use tordns on another container. 
```
docker network create tor
```
tordns will resolve your .onion quries and it out of the box does not need any configurating. \
You can check logs to see responses for more Check on [DockerHUB](https://hub.docker.com/repository/docker/amjiddader/tordns) \
```
docker run --name tordns --restart=always -dit -p 127.0.0.9:53:5353/udp --network tor --dns 1.1.1.1  amjiddader/tordns
```
Check IP of tordns in case you dont use network and want to use tordns dns in same server but on new docker network and container .
```
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}} {{end}}'  tordns
```

## 2 TOR Search Engine. 
yacy_search_server [Availabel on Github](https://github.com/yacy/yacy_search_server) ) 

```
docker run -d --name torsearch -p 8090:8090 -v /home/search/data:/opt/yacy_search_server/DATA --restart unless-stopped --log-opt max-size=200m --log-opt max-file=2 amjiddader/tor_search:latest
```
As anove docker image i make this privete and i many not update this i recommend using below.
```
docker run -d --name yacy_search_server -p 8090:8090 -p 8443:8443 --dns 127.0.0.9  --dns 127.0.0.9  --network tor -v yacy_search_server_data:/opt/yacy_search_server/DATA --restart unless-stopped --log-opt max-size=200m --log-opt max-file=2 yacy/yacy_search_server:latest
```
