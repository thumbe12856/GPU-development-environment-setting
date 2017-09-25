# Install Cuda-8.0
First, install NVIDIA driver.
```
$ sudo -s
$ add-apt-repository ppa:graphics-drivers/ppa
$ apt-get update
$ reboot
```

Open your System Settings -> Software & Updates -> ADditional Drivers, and you will see NVIDIA Corporation. Choose "Using NVIDIA binary driver - version 378.13 from nvidia-378(open source)" and click button Apply Changes.
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get dist-upgrade
$ sudo ./install_lib.sh
$ sudo reboot
```
Add the configures to /etc/modprobe.d/blacklist-nouveau.conf
```
blacklist nouveau
options nouveau modeset=0
```
Go to https://developer.nvidia.com/cuda-downloads and download Cuda8.0 runfile for Ubuntu16.04, and then run it.
```
$ sudo update-initramfs -u
$ sudo sh cuda_8.0.61_375.26_linux.run
```
If you see the result under below, that means you install cuda-8.0 succeed.
```
===========
= Summary =
===========
Driver:     Not Selected
Tookit      Installed in /usr/local/cuda-8.0
Samples:    Installed in /home/user
```
Install NVIDIA xconfig
```
$ sudo nvidia-xconfig
$ sudo reboot
```
For Bash. Set the cuda and its library's path.
```
$ vi ~/.profile
export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda-8.0/lib64"
export CUDA_HOME=/usr/local/cuda-8.0/
$ source ~/.profile
```
Install cuda samples.
```
$ cuda-install-samples-8.0.sh ~/
```

# Run
Test nvcc.
```
$ nvcc --version
```
It will output something like this:
```
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2016 NVIDIA Corporation
Built on Tue_Jan_10_13:22:03_CST_2017
Cuda compilation tools, release 8.0, V8.0.61
```
Test the cuda sample code, ~/NVIDIA_CUDA-8.0_Samples/1_Utilities/deviceQuery
```
$ cd ~/NVIDIA_CUDA-8.0_Samples/1_Utilities/deviceQuery
$ make
$ ./deviceQuery
```
It will output the detail of your GPU card.
