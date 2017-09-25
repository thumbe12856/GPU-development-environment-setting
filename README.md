# GPU development environment setting
This is for Ubuntu16.04 with cuda8.0. Using python library, Theano, to implement deep learning with Nvidia GPU.
Note that, all tool's version are important!

# Dependencies
- [Ubuntu 16.04](http://breakdance.io)
- NVIDIA GPU
  - [Cuda 8.0](https://developer.nvidia.com/cuda-download)
  - [cuDNN 5.0](https://developer.nvidia.com/cudnn)
- Deep Learning tool
  - [Theano 0.9](https://github.com/Theano/Theano)
  - [libgpuarray 0.7.3](http://deeplearning.net/software/libgpuarray/installation.html)
  - [Lasagne 0.1](https://github.com/Lasagne/Lasagne)
  - [Arcade-Learning-Environment](https://github.com/mgbellemare/Arcade-Learning-Environment)
- Deep Learning Project
  - [deep_q_rl](https://github.com/spragunr/deep_q_rl)
  - [Q-Optimality-Tightening](https://github.com/ShibiHe/Q-Optimality-Tightening)

Because Theano now only supports to cuDNN with version 5.1. And the project deep_q_rl (https://github.com/spragunr/deep_q_rl) need gpuarray with version 0.7.0 or newer, for now, can not install gpuarray from github. Please make sure the version of Theano is compatible with the one of Lasagne.


# Install
First, install [cuda](https://github.com/thumbe12856/GPU-development-environment-setting/tree/master/cuda) and [cuDNN](https://github.com/thumbe12856/GPU-development-environment-setting/tree/master/cuDNN).
Secondly, install Theano and gpuarray.

# Run
Finally, testing with Deep Learning projects.
