# GPU development environment setting
This is for Ubuntu16.04 with cuda8.0. Using python library, Theano, to implement deep learning with Nvidia GPU.
Note that, all tool's version are important!

# Dependencies
- [Ubuntu 16.04](http://breakdance.io)
- Nvidia GPU
  - [Cuda 8.0](https://developer.nvidia.com/cuda-download)
  - [cuDNN 5.0](https://developer.nvidia.com/cudnn)
- Deep Learning tool
  - [Theano 0.9](https://github.com/Theano/Theano)
  - [libgpuarray 7.3](http://deeplearning.net/software/libgpuarray/installation.html)
  - [Lasagne 0.1](https://github.com/Lasagne/Lasagne)
  - [Arcade-Learning-Environment](https://github.com/mgbellemare/Arcade-Learning-Environment)
- Deep Learning Project
  - [deep_q_rl](https://github.com/spragunr/deep_q_rl)
  - [Q-Optimality-Tightening](https://github.com/ShibiHe/Q-Optimality-Tightening)

Because Theano now only supports to cuDNN with version 5.1. And the project deep_q_rl (https://github.com/spragunr/deep_q_rl) need gpuarray at least version 7.0, for now, can not install gpuarray from github. Please make sure the version of Theano is compatible with the one of Lasagne.

