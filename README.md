# Release 2.17.0 corresponding to NGC container 21.12 with Python Backend

A release of Triton for JetPack 4.6 (https://developer.nvidia.com/embedded/jetpack) is provided in the attached tar file: tritonserver2.17.0-jetpack4.6-py.tgz.

This release supports TensorFlow 2.6.0, TensorFlow 1.15.5, TensorRT 8.0.1.6, Onnx Runtime 1.10.0 and as well as ensembles (Python Backend supported).
For the Onnx Runtime backend the OpenVino execution provider is not supported but the TensorRT execution provider is supported.
System shared memory is supported on Jetson.
GPU metrics, GCS storage, S3 storage and Azure storage are not supported.
The tar file contains the Triton server executable and shared libraries and also the C++ and Python client libraries and examples.

