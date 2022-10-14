## 👋 Welcome to podman 🚀  

Description  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update podman
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/podman/dataDir"
git clone "https://github.com/dockermgr/podman" "$HOME/.local/share/CasjaysDev/dockermgr/podman"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/podman/dataDir/." "$HOME/.local/share/srv/docker/podman/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/podman:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-podman \
--hostname casjaysdev-podman \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/podman/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/podman/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/podman:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  podman:
    image: casjaysdevdocker/podman
    container_name: podman
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-podman
    volumes:
      - $HOME/.local/share/srv/docker/podman/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/podman/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
📽  dockermgr: [Github](https://github.com/dockermgr) [Docker](https://hub.docker.com/r/dockermgr) 📽  
⛵ CasjaysDev Docker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
