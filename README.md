# TOR , DARKWEB

This repo contains personal and public repos/apps/softwares that are useful for TOR. \
Warning: I do not endorse anyone to use Darkweb as it is very serious and dengerous...

## 1 TOR DNS RESOLVER 
tordns will resolve your .onion quries and it out of the box does not need any configurating. \
You can check logs to see responses for more Check on [DockerHUB](https://hub.docker.com/repository/docker/amjiddader/tordns) \
docker run --name tordns --restart=always -dit -p 127.0.0.9:53:5353/udp --dns 1.1.1.1 - amjiddader/tordns


## 2 TOR Search Engine. 
yacy_search_server [Availabel on Github](https://github.com/yacy/yacy_search_server) ) \
docker run -d --name torsearch -p 8090:8090 -v /home/search/data:/opt/yacy_search_server/DATA --restart unless-stopped --log-opt max-size=200m --log-opt max-file=2 yacy/yacy_search_server:latest
