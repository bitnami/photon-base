[![CircleCI](https://circleci.com/gh/bitnami/photon-base.svg?style=svg)](https://circleci.com/gh/bitnami/photon-base)

# `bitnami/photon-base`

## TL;DR

```dockerfile
FROM bitnami/photon-base
```

## About

The `bitnami/photon-base` image is a customized base image for use in Bitnami container images and is built on top of the optimized (Photon OS image)[https://hub.docker.com/r/library/photon/] from Docker Hub.

The `Dockerfile` installs some basic system packages, performs some security actions and includes a `install_packages` script to install new system packages using the minimum amount of space.

## Usage

Use like a regular base image.

The following example uses the `install_packages` helper script to install packages from the Photon repositories using `tdnf`.

```dockerfile
FROM bitnami/photon-base:3
RUN install_packages wget apr apr-util bzip2-libs glibc
CMD ["bash"]
```

## Configuration Parameters

The following tables lists the configurable parameters of the image.

|         Parameter         |                       Description                       |
|---------------------------|---------------------------------------------------------|
| `DISABLE_WELCOME_MESSAGE` | [Turn off the welcome text](#turn-off-the-welcome-text) |

### Turn off the welcome text

When a new container is launched, a welcome message is displayed as illustrated below:

```console
 *** Welcome to the apache image ***
 *** Brought to you by Bitnami ***
 *** More information: https://github.com/bitnami/bitnami-docker-apache ***
 *** Issues: https://github.com/bitnami/bitnami-docker-apache/issues ***
```

Adding `DISABLE_WELCOME_MESSAGE=1` to the container environment turns off this message.

## Contributing

We'd love for you to contribute to this container. You can request new features by creating an [issue](../../issues/new) or submitting a [pull request](../../issues/pull) with your contribution.

### Issues

If you encountered a problem running this container, you can file an [issue](../../issues/new). Be sure to include the following information in your issue:

- Host OS and version
- Output of:
  + `docker version`
  + `docker info`
- Steps to reproduce the issue
- Logging information with debug mode enabled

## License

Copyright 2019 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

