# Gitlab Runner packaged by Bitnami

## What is Gitlab Runner?

> Gitlab Runner is an auxiliary application for Gitlab installations. Written in Go, it allows to run CI/CD jobs and send the results back to Gitlab.

[Overview of Gitlab Runner](https://gitlab.com/gitlab-org/gitlab-runner/)

Trademarks: This software listing is packaged by Bitnami. The respective trademarks mentioned in the offering are owned by the respective companies, and use of them does not imply any affiliation or endorsement.

## TL;DR

```console
$ docker run -it --name gitlab-runner bitnami/gitlab-runner
```

### Docker Compose

```console
$ curl -sSL https://raw.githubusercontent.com/bitnami/containers/main/bitnami/gitlab-runner/docker-compose.yml > docker-compose.yml
$ docker-compose up -d
```

## Why use Bitnami Images?

* Bitnami closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Bitnami images the latest bug fixes and features are available as soon as possible.
* Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* All our images are based on [minideb](https://github.com/bitnami/minideb) a minimalist Debian based container image which gives you a small base container image and the familiarity of a leading Linux distribution.
* All Bitnami images available in Docker Hub are signed with [Docker Content Trust (DCT)](https://docs.docker.com/engine/security/trust/content_trust/). You can use `DOCKER_CONTENT_TRUST=1` to verify the integrity of the images.
* Bitnami container images are released on a regular basis with the latest distribution packages available.

## Supported tags and respective `Dockerfile` links

Learn more about the Bitnami tagging policy and the difference between rolling tags and immutable tags [in our documentation page](https://docs.bitnami.com/tutorials/understand-rolling-tags-containers/).


* [`15`, `15-debian-11`, `15.3.0`, `15.3.0-debian-11-r9`, `latest` (15/debian-11/Dockerfile)](https://github.com/bitnami/containers/blob/main/bitnami/gitlab-runner/15/debian-11/      Dockerfile)

Subscribe to project updates by watching the [bitnami/containers GitHub repo](https://github.com/bitnami/containers).

## Get this image

The recommended way to get the Bitnami Gitlab Runner Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bitnami/gitlab-runner).

```console
$ docker pull bitnami/gitlab-runner:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/bitnami/gitlab-runner/tags/) in the Docker Hub Registry.

```console
$ docker pull bitnami/gitlab-runner:[TAG]
```

If you wish, you can also build the image yourself by cloning the repository, changing to the directory containing the Dockerfile and executing the `docker build` command. Remember to replace the `APP`, `VERSION` and `OPERATING-SYSTEM` path placeholders in the example command below with the correct values.

```console
$ git clone https://github.com/bitnami/containers.git
$ cd bitnami/APP/VERSION/OPERATING-SYSTEM
$ docker build -t bitnami/APP:latest .
```

## Maintenance

### Upgrade this image

Bitnami provides up-to-date versions of Gitlab Runner, including security patches, soon after they are made upstream. We recommend that you follow these steps to upgrade your container.

#### Step 1: Get the updated image

```console
$ docker pull bitnami/gitlab-runner:latest
```

or if you're using Docker Compose, update the value of the image property to `bitnami/gitlab-runner:latest`.

#### Step 2: Remove the currently running container

```console
$ docker rm -v gitlab-runner
```

or using Docker Compose:

```console
$ docker-compose rm -v gitlab-runner
```

#### Step 3: Run the new image

Re-create your container from the new image.

```console
$ docker run --name gitlab-runner bitnami/gitlab-runner:latest
```

or using Docker Compose:

```console
$ docker-compose up gitlab-runner
```

## Configuration

### Running commands

To run commands inside this container you can use `docker run`, for example to execute `gitlab-runner --help` you can follow the example below:

```console
$ docker run --rm --name gitlab-runner bitnami/gitlab-runner:latest --help
```

Check the [official Gitlab Runner documentation](https://docs.gitlab.com/runner/commands/) for the list of the available parameters.

## Contributing

We'd love for you to contribute to this Docker image. You can request new features by creating an [issue](https://github.com/bitnami/containers/issues), or submit a [pull request](https://github.com/bitnami/containers/pulls) with your contribution.

## Issues

If you encountered a problem running this container, you can file an [issue](https://github.com/bitnami/containers/issues/new/choose). For us to provide better support, be sure to fill the issue template.

## License

Copyright &copy; 2022 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
