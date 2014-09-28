# ipxe-builder

## Usage

```
docker run -v /home/core/ipxe-builder/bin:/ipxe/src/bin \
quay.io/kelseyhightower/ipxe-builder \
make bin/undionly.kpxe
```

## Build

```
docker build -t quay.io/kelseyhightower/ipxe-builder .
```
