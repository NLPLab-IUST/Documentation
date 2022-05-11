========================
Triton
========================

The NVIDIA Container Toolkit allows users to build and run GPU accelerated 
containers. The toolkit includes a container runtime library and utilities to 
automatically configure containers to leverage NVIDIA GPUs.

.. tip::
    **Reference Links**
    * *Triton*
        * `Quickstart Guide <https://github.com/triton-inference-server/server/blob/r20.12/docs/quickstart.md>`_
        * `Triton Inference Server \(Formerly TensorRT inference Server\) <https://catalog.ngc.nvidia.com/orgs/nvidia/containers/tritonserver>`_
        * `Triton Inference Server GitHub <https://github.com/triton-inference-server/server>`_

    * `Nvidia Docker <https://github.com/NVIDIA/nvidia-docker>`_
    * `NVIDIA Cloud Native Technologies Documentation Website <https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/overview.html>`_
    * `Install Docker Engine <https://docs.docker.com/engine/install/>`_

nvidia-docker2 package is installed

==============
Installation
==============

#. first Install Docker with the links on the Top
#. Pull the image using the following command.
        * docker pull 'nvcr.io/nvidia/tritonserver:22.04-py3'
