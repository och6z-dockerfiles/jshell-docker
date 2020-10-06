# JShell-docker
```bash
docker build \
    --no-cache \
    --build-arg IMAGE=adoptopenjdk/openjdk11 \
    --build-arg IMAGE_VERSION=alpine-slim \
    --build-arg GLIBC_VER=2.32-r0 \
    --build-arg GCC_LIBS_VER=9.2.0-4 \
    --build-arg ZLIB_VER=1:1.2.11-4 \
    --file Dockerfile.alpine \
    --tag image-name:version .
```
```bash
xhost +local:docker
```
```bash
docker container run \
    --interactive \
    --tty \
    --volume /tmp/.X11-unix:/tmp/.X11-unix \
    --env DISPLAY=unix$DISPLAY \
    --name container-name image-name:version
```
