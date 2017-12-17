# Feed-The-Beast Horizons III (Modded Minecraft 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_horizons3:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_horizons3_data
docker volume create minecraft_ftb_horizons3_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_horizons3 \
    --volume minecraft_ftb_horizons3_data:/minecraft/world \
    --volume minecraft_ftb_horizons3_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_horizons3:stable
```
