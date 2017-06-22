# QGIS snap

This project creates a working snap of QGIS (www.qgis.org).
QGIS is a Geographic Information System (GIS) that supports vector, raster & database formats

## Current state
* Only amd64
* Working QCA OpenSSL - fixed `Authentication System: DISABLED` message 

## Building the snap
On an Ubuntu system a snap can be built out of the `snapcraft.yaml` by running `snapcraft` in the project directory.

For a clean, system independent build it is recommanden to use the official `snapcore/snapcraft` Docker image. Using Docker, you’ll map the current directory into the container and then build the snap from that same directory:
```
docker pull snapcore/snapcraft
docker run -v $PWD:$PWD -w $PWD snapcore/snapcraft bash -c "apt update && apt upgrade -y && snapcraft clean && snapcraft"
```
