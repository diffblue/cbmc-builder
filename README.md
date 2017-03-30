# CBMC Builder Docker Images [![Build Status](https://travis-ci.org/diffblue/cbmc-builder.svg?branch=master)](https://travis-ci.org/diffblue/cbmc-builder)

This is the Git repo of the Docker images for building
[CBMC](https://github.com/diffblue/cbmc) in/for different operating systems.

Builders exist for two OS:
- alpine in [alpine/Dockerfile](alpine/Dockerfile) referenced as
  `diffblue/cbmc-builder:alpine`,
  `diffblue/cbmc-builder:alpine-0.0.1`
- ubuntu in [ubuntu/Dockerfile](ubuntu/Dockerfile) referenced as
  `diffblue/cbmc-builder:latest`,
  `diffblue/cbmc-builder:xenial`,
  `diffblue/cbmc-builder:xenial-0.0.1`

## To compile CBMC source manually

Set path to your cloned CBMC source

```bash
CBMC_PATH=~/git/cbmc
```

To run compilation [instructions](https://github.com/diffblue/cbmc/blob/master/COMPILING)
in container

```bash
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C src minisat2-download
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C src -j$(getconf _NPROCESSORS_ONLN)
```

To run tests afterwards

```bash
docker run --rm -v ${CBMC_PATH}:/cbmc diffblue/cbmc-builder make -C regression test
```

## To compile CBMC source using *dobi*

Install [dobi](https://github.com/dnephin/dobi/) and add it to your `PATH`.

Enter to folder with `dobi.yml` (root of this repository).

To run all tasks

```bash
BUILD_TAG=$(git describe) dobi
```

To run all tests

```bash
BUILD_TAG=$(git describe) dobi test
```

Remove all temporary files

```bash
BUILD_TAG=$(git describe) dobi clean
```
