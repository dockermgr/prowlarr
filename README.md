## 👋 Welcome to prowlarr 🚀  

Prowlarr is a indexer manager/proxy built on the popular arr .net/reactjs base stack to integrate with your various PVR apps.  Prowlarr supports both Torrent Trackers and Usenet Indexers. It integrates seamlessly with Sonarr, Radarr, Lidarr, and Readarr.  offering complete management of your indexers with no per app Indexer setup required  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update prowlarr
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/prowlarr/volumes"
git clone "https://github.com/dockermgr/prowlarr" "$HOME/.local/share/CasjaysDev/dockermgr/prowlarr"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/prowlarr/volumes/." "$HOME/.local/share/srv/docker/prowlarr/volumes/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-prowlarr \
--hostname prowlarr \
-e PUID=1000 \
-e PGID=1000 \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-prowlarr/volumes/config:/config:z \
-p 0.0.0.0:9696:9696 \
casjaysdevdocker/prowlarr:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/prowlarr
    container_name: casjaysdevdocker-prowlarr
    environment:
      - TZ=America/New_York
      - HOSTNAME=prowlarr
    volumes:
      - $HOME/.local/share/srv/docker/casjaysdevdocker-prowlarr/volumes/data:/data:z
      - $HOME/.local/share/srv/docker/casjaysdevdocker-prowlarr/volumes/config:/config:z
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/prowlarr
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/prowlarr" "$HOME/Projects/github/casjaysdevdocker/prowlarr"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/prowlarr"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
