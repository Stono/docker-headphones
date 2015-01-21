# docker-headphones
This is a [headphones](https://github.com/rembo10/headphones) docker container.

The easiest way to use this is probably a fig file:
```
headphones:
  image: stono/headphones 
  volumes:
    - ./storage:/storage
  ports:
    - "8181:8181"
```
From there you can start it with `sudo fig up -d` and connect to it on:
  - http://127.0.0.1:8181

Or if you don't want to use fig, this will do the job:
```
sudo docker run -d && \
  -v "/home/karl/development/git/github/docker-headphones/storage:/storage" && \
  -p "8181:8181" stono/headphones
```

## Storage
All config / data gets written to /storage/headphones on the first "fig up", so if you mount in that volume to somewhere on your system, all your configuration will be preserved through docker container updates.

You could mount in your own, already existing config directory if you like.

## Info 
This is part of a set, all based of the same images, all desgined to eventually piece together.
  - [stono/sonarr](https://github.com/Stono/docker-sonarr) Sonarr in a Docker container
  - [stono/nzbget](https://github.com/Stono/docker-nzbget) NzbGet in a Docker container
  - [stono/couchpotato](https://github.com/Stono/docker-couchpotato) Couchpotato in a docker container
