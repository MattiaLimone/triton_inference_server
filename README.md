<div text-align="justify">
  
# Triton Inference Server for Jetson JetPack

This repository provides Triton Inference Server support for Jetson JetPack, specifically tested with JetPack 4.6. 

Triton Inference Server is a high-performance inference serving software that lets you deploy machine learning models in production environments.

## Release Information

The release package (`tritonserver2.17.0-jetpack4.6-py.tgz`) includes the Triton server executable, shared libraries, C++ and Python client libraries, and examples. The release supports the following frameworks and versions:
- TensorFlow 2.6.0
- TensorFlow 1.15.5
- TensorRT 8.0.1.6
- ONNX Runtime 1.10.0
- Ensembles (Python Backend supported)

Please note the specific compatibility and features outlined in the detailed release notes.

## Local Usage

### Prerequisites

Before running Triton locally on your Jetson device (tested on [Jetson Nano Ubuntu 20](https://github.com/Qengineering/Jetson-Nano-Ubuntu-20-image)), ensure the following dependencies are installed:

```bash
apt-get update && \
    apt-get install -y --no-install-recommends \
        software-properties-common \
        autoconf \
        automake \
        build-essential \
        cmake \
        git \
        libb64-dev \
        libre2-dev \
        libssl-dev \
        libtool \
        libboost-dev \
        libcurl4-openssl-dev \
        libopenblas-dev \
        rapidjson-dev \
        patchelf \
        zlib1g-dev
```

### Installation

Download and unzip the Triton release package:

```bash
wget https://github.com/MattiaLimone/triton_inference_server/releases/download/v2.17.0/tritonserver2.17.0-jetpack4.6-py.tgz
tar xf tritonserver2.17.0-jetpack4.6-py.tgz -C /opt/triton/.
rm tritonserver2.17.0-jetpack4.6-py.tgz
```

Set environment variables for Triton:

```bash
export PATH=/opt/triton/bin:$PATH
export LD_LIBRARY_PATH=/opt/triton/lib:$LD_LIBRARY_PATH
```

For persistent configuration, add the above export commands to your `~/.bashrc` file.

## Docker Usage

### Building the Docker Image

To use Triton Inference Server within a Docker container (tested on [Jetson Nano Ubuntu 20](https://github.com/Qengineering/Jetson-Nano-Ubuntu-20-image)), follow these steps:

1. Download the Dockerfile:
   ```bash
   wget https://github.com/MattiaLimone/triton_inference_server/releases/download/v2.17.0/Dockerfile
   ```

2. Build the Docker image:
   ```bash
   docker build <path-to-docker-file> -t jetson/tritonserver:21.12-py3
   ```

### Running Triton Server in Docker

To run Triton server in the Docker container, use the following command:

```bash
docker run -it jetson/tritonserver:21.12-py3 /bin/bash -c "tritonserver $ARGS"
```

Replace `$ARGS` with the desired Triton server command-line arguments.

---

## Author
Mattia Limone - [mattia.limone@leonardo.com](mailto:mattia.limone@leonardo.com)
</div>
