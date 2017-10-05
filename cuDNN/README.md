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
$ sudo chmod a+r /usr/local/cuda-8.0/lib64/libcudnn*
```

If you did not set the cudnn well, when import theano in python, the system may output the error that could not find cudnn library like this:
RuntimeError: Could not find cudnn library

You may reset the cudnn path.
```
$ cd folder/extracted/contents
$ sudo cp -P include/cudnn.h /usr/include
$ sudo cp -P lib64/libcudnn* /usr/lib/x86_64-linux-gnu/
$ sudo chmod a+r /usr/lib/x86_64-linux-gnu/libcudnn*
```
