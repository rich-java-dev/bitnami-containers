# KSQL DB packaged by Bitnami

## What is ksql?

> Confluent KSQL DB is an event streaming database that helps you build stream processing apps

[Overview of ksql](https://change.me)



## TL;DR

```console
$ docker run --name ksql bitnami/ksql:latest
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


* [`7.2`, `7.2-debian-11`, `7.2.1`, `7.2.1-debian-11-r11`, `latest` (7.2/debian-11/Dockerfile)](https://github.com/bitnami/containers/blob/main/bitnami/ksql/7.2/debian-11/Dockerfile)
* [`7.1`, `7.1-debian-11`, `7.1.3`, `7.1.3-debian-11-r15` (7.1/debian-11/Dockerfile)](https://github.com/bitnami/containers/blob/main/bitnami/ksql/7.1/debian-11/Dockerfile)
* [`7.0`, `7.0-debian-11`, `7.0.5`, `7.0.5-debian-11-r15` (7.0/debian-11/Dockerfile)](https://github.com/bitnami/containers/blob/main/bitnami/ksql/7.0/debian-11/Dockerfile)
* [`6.2`, `6.2-debian-11`, `6.2.6`, `6.2.6-debian-11-r15` (6.2/debian-11/Dockerfile)](https://github.com/bitnami/containers/blob/main/bitnami/ksql/6.2/debian-11/Dockerfile)
* [`6.1`, `6.1-debian-11`, `6.1.7`, `6.1.7-debian-11-r16` (6.1/debian-11/Dockerfile)](https://github.com/bitnami/containers/blob/main/bitnami/ksql/6.1/debian-11/Dockerfile)
* [`6.0`, `6.0-debian-11`, `6.0.9`, `6.0.9-debian-11-r15` (6.0/debian-11/Dockerfile)](https://github.com/bitnami/containers/blob/main/bitnami/ksql/6.0/debian-11/Dockerfile)

Subscribe to project updates by watching the [bitnami/containers GitHub repo](https://github.com/bitnami/containers).

## Get this image

The recommended way to get the Bitnami ksql Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bitnami/ksql).

```console
$ docker pull bitnami/ksql:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/bitnami/ksql/tags/) in the Docker Hub Registry.

```console
$ docker pull bitnami/ksql:[TAG]
```

If you wish, you can also build the image yourself by cloning the repository, changing to the directory containing the Dockerfile and executing the `docker build` command. Remember to replace the `APP`, `VERSION` and `OPERATING-SYSTEM` path placeholders in the example command below with the correct values.

```console
$ git clone https://github.com/bitnami/containers.git
$ cd bitnami/APP/VERSION/OPERATING-SYSTEM
$ docker build -t bitnami/APP:latest .
```

## Branch Deprecation Notice

ksql's branch 6.0.x is no longer maintained by upstream and is now internally tagged as to be deprecated. This branch will no longer be released in our catalog a month after this notice is published, but already released container images will still persist in the registries. Valid to be removed starting on: 09-24-2022

## Contributing

We'd love for you to contribute to this container. You can request new features by creating an [issue](https://github.com/bitnami/containers/issues), or submit a [pull request](https://github.com/bitnami/containers/pulls) with your contribution.

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
