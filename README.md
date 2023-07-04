## 👋 Welcome to prowlarr 🚀  

prowlarr README  
  
  
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
mkdir -p "$HOME/.local/share/srv/docker/prowlarr/rootfs"
git clone "https://github.com/dockermgr/prowlarr" "$HOME/.local/share/CasjaysDev/dockermgr/prowlarr"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/prowlarr/rootfs/." "$HOME/.local/share/srv/docker/prowlarr/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-prowlarr \
--hostname prowlarr \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-prowlarr/rootfs/data:/data:z \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-prowlarr/rootfs/config:/config:z \
-p 80:80 \
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
      - $HOME/.local/share/srv/docker/casjaysdevdocker-prowlarr/rootfs/data:/data:z
      - $HOME/.local/share/srv/docker/casjaysdevdocker-prowlarr/rootfs/config:/config:z
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
