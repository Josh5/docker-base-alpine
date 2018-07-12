
# josh5/docker-base-alpine

### Based upon [Alpine Linux](https://hub.docker.com/_/alpine/) and [S6 overlay](https://github.com/just-containers/s6-overlay), this serves as a base template container for all other docker containers created by Josh.5.

### Builds "josh5/base-alpine:<VERSION>"

```
ALPINE_VERSION=3.7
docker build -t josh5/base-alpine:${ALPINE_VERSION} .
```
