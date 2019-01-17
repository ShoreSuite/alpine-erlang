alpine-erlang
===

alpine-erlang Docker image builder, largely based on [bitwalker/alpine-erlang](https://github.com/bitwalker/alpine-erlang) but modified to allow use of Docker [build arguments](https://docs.docker.com/engine/reference/commandline/build/#set-build-time-variables---build-arg) and to take advantage of [multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/) for a slightly smaller distribution image.

## Usage Instructions

To simply use the latest, published Docker image

```
docker pull shoresuite/alpine-erlang
```

However, it's recommended that you specify the exact image version (based on Erlang/OTP version)

```
docker pull shoresuite/alpine-erlang:21.2.2
```

## Build Instructions

To build and tag the image yourself locally, first clone this repository then

```
ERLANG_VERSION=$(cat VERSION|tr -d '\n'); docker build -t alpine-erlang:${ERLANG_VERSION} --build-arg ERLANG_VERSION=${ERLANG_VERSION} .
```

You may also try to build using an older version of Erlang, by supplying your own value for `ERLANG_VERSION`. For example

```
ERLANG_VERSION='21.1.4'; docker build -t alpine-erlang:${ERLANG_VERSION} --build-arg ERLANG_VERSION=${ERLANG_VERSION} .
```
