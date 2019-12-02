# Avorion Docker [![Docker Stars][4]][2] [![Docker Pulls][5]][2]

[Avorion][0] dedicated server

Branch | Size             | Version          
-------|------------------|---------------
latest | [![Size][6]][2]  | [![Version][7]][2]
stable | [![Size][8]][2]  | [![Version][9]][2]
beta   | [![Size][10]][2] | [![Version][11]][2]

## Usage

### Quickstart

```
docker run -d --name avorion -p 27000:27000 -p 27000:27000/udp -p 27003:27003/udp -p 27020:27020/udp -p 27021:27021/udp rfvgyhn/avorion
```

### Volumes

* `/home/steam/.avorion/galaxies/avorion_galaxy` mount for galaxy save and server configuration

```
docker run -d --name avorion \
   -p 27000:27000 \
   -p 27000:27000/udp \
   -p 27003:27003/udp \
   -p 27020:27020/udp \
   -p 27021:27021/udp \
   -v /host/path/saves:/home/steam/.avorion/galaxies/avorion_galaxy \
   rfvgyhn/avorion
```

### Configuration

Default settings will be generated and placed in the `/home/steam/.avorion/galaxies/avorion_galaxy` volume. To make changes, stop the container, modify the desired files and then restart the container.

If you enable RCON in `settings.ini`, make sure you also forward the port in docker (`-p 27015:27015`).

## Docker Images

The `latest` tag will follow the latest [avorion server][1] release
(including beta releases).

The `stable` tag will follow the latest stable (non-beta) [avorion server][1] release.

You can specify a specific version using the available [tags][3]


[0]: https://www.avorion.net/
[1]: https://www.avorion.net/forum/index.php/board,2.0.html
[2]: https://hub.docker.com/r/rfvgyhn/avorion
[3]: https://hub.docker.com/r/rfvgyhn/avorion/tags
[4]: https://img.shields.io/docker/stars/rfvgyhn/avorion.svg
[5]: https://img.shields.io/docker/pulls/rfvgyhn/avorion.svg
[6]: https://images.microbadger.com/badges/image/rfvgyhn/avorion.svg
[7]: https://img.shields.io/badge/v-0.29.3--beta-blue
[8]: https://images.microbadger.com/badges/image/rfvgyhn/avorion:stable.svg
[9]: https://img.shields.io/badge/v-0.28.1-blue
[10]: https://images.microbadger.com/badges/image/rfvgyhn/avorion:0.29.3-beta.svg
[11]: https://img.shields.io/badge/v-0.29.3--beta-blue
