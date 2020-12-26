# nes-web
[![travis][travis-badge]][travis-url] [![appveyor][appveyor-badge]][appveyor-url] ![license][license-badge]

[Demo](https://game.nfam.me)

Multiplayer Online Classic NES Games on Web Browser, using [`WebRTC`](https://webrtc.org) Peer to Peer connection.

- Supports Gamepad.
- Supports Gamepad Simulation (Keyboard).
- Supports Fullscreen.
- Supports multiple languages.

![Catalog][1]
![Multiplayer][2]

## How to use this image

### Build Docker image

On amd64 platforms, please run the following command.

```shell
sudo docker build -f docker/amd64.Dockerfile -t leimao/nes-web-amd64 .
```

On arm64 platforms, please run the following command.

```shell
sudo docker build -f docker/arm64.Dockerfile -t leimao/nes-web-arm64 .
```

### Run on host networking

This example uses host networking for simplicity. Also note the `-v` argument. This directory will be used to store `NES` roms and screen images.

```shell
sudo docker run -d --rm \
    -p 8080:8080 \
    -v $(pwd)/data:/data \
    leimao/nes-web-amd64
```

- ROM file names in /data/roms must end with `.nes` extension.
- Screen images must have `.png` and have the same base name with the corresponding ROM.

#### HTML

Just navigate to `http://{{address}}:8080/`.

[1]: catalog.png
[2]: multiplayer.png

[travis-badge]: https://travis-ci.org/nfam/nes-web.svg
[travis-url]: https://travis-ci.org/nfam/nes-web
[appveyor-badge]: https://ci.appveyor.com/api/projects/status/github/nfam/nes-web?svg=true
[appveyor-url]: https://ci.appveyor.com/project/nfam/nes-web/
[license-badge]: https://img.shields.io/github/license/nfam/nes-web.svg
