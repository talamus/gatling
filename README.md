# Base Docker Image

* [java:8-jdk-alpine](https://registry.hub.docker.com/_/java/)

# Docker Tags

* 3.0.3 (latest)

[![CircleCI](https://circleci.com/gh/denvazh/gatling/tree/master.svg?style=svg)](https://circleci.com/gh/denvazh/gatling/tree/master)
[![](https://images.microbadger.com/badges/image/denvazh/gatling.svg)](http://microbadger.com/images/denvazh/gatling "Get your own image badge on microbadger.com")

Note: Gatling versions from 2.1.0 to 2.2.5 are built with Scala 2.11, versions from 2.3.0 onwards are built with Scala 2.12.

# Installation

* Install [Docker](https://www.docker.com/)

* Get automated build from public registry:

Latest version:

`docker pull denvazh/gatling:latest`

All versions:

`docker pull denvazh/gatling`

Specific version:

`docker pull denvazh/gatling:3.0.3`

* [Alternatively] Build an image from Dockerfile: `docker build -t="denvazh/gatling" github.com/denvazh/gatling`

# Usage

Use image to run container

```
docker run -it --rm denvazh/gatling
```

Mount configuration and simulation files from the host machine and run gatling in interactive mode

```
docker run -it --rm -v /home/core/gatling/conf:/opt/gatling/conf \
-v /home/core/gatling/user-files:/opt/gatling/user-files \
-v /home/core/gatling/results:/opt/gatling/results \
denvazh/gatling
```

Use the `-e` switch to use JAVA_OPTS to pass parameters to gatling tests

```
docker run -e JAVA_OPTS="-Dusers=10" -it --rm denvazh/gatling
```

# Command line arguments

Command line arguments for Compiler and Gatling can be sent via environment variables:

* `COMPILER_ARGS`
* `GATLING_ARGS`

Or by text files located in the `gatling/conf` volume:

* `compiler_args.txt`
* `gatling_args.txt`
