# Install cuDNN-5.0
Make a cuDNN directory at your home.
```
mkdir ~/cuDNN
```
Go to https://developer.nvidia.com/cudnn, and download the tgz file, cuDNN version 5.0 for CUDA-8.0, then unzip it to ~/cuDNN. Copy the library and cudnn.h to /usr/local/cuda-8.0/.
```
$ cd ~/cuDNN
$ tar -xzvf cudnn-8.0-linux-x64-v5.0-ga.tgz
$ sudo cp ~/cuDNN/cuda/lib64/lib* /usr/local/cuda-8.0/lib64/
$ sudo cp ~/cuDNN/cuda/include/cudnn.h /usr/local/cuda-8.0/include/
```
