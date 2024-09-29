# Juniper AWX Execution Environment

This repository contains the necessary files to build a Docker image that can be used as an execution environment for Juniper devices in AWX.

This is meant to be the simplest, most straightforward way to get the `juniper.device` collection working in AWX.

Note that there is one prerequisite: you must have >= version 3.1.0 of `ansible-builder` installed. You can install it with pip:

```bash
pip install ansible-builder
```

Double check that you have the correct version:

```bash
ansible-builder --version
```

3.0 won't work, you need 3.1.0 or later.

## Building the image

To build the image, simply run the following command (if you have `podman` installed, you can use `--container-runtime=podman` instead of `--container-runtime=docker`):

```bash
ansible-builder build -v3.1 -t awx-ee-juniper:latest --container-runtime=docker
```

This execution environment is [available on Docker Hub](https://hub.docker.com/r/levtolstoi/awx-ee-juniper).
