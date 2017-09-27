# Install Theano, Lasagne and gpuarray
Before install Theano, there are some python dependencies, conda, virtaulenv, and [Arcade Learning Environment](https://github.com/mgbellemare/Arcade-Learning-Environment), [Pylearn2](https://github.com/lisa-lab/pylearn2) and theano configuration to set up.

First, set pip configuration.
```
$ sudo apt install python-pip python3-pip
$ cd
$ mkdir .pip
$ vi ~/.pip/pip.conf
[list]
format=columns
```
Set the .theanorc at your home. For now, the device value is gpu,  we will change it to cuda* for the newer GPU backend.
```
$ vi ~/.theanorc
[cuda]
root=/usr/local/cuda

[global]
device = gpu
floatX = float32
```
Install virtualenv and Miniconda. Restart your terminal, and you can use conda to install python lib.
```
$ sudo apt-get install virtualenv 

$ wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh
$ bash Miniconda2-latest-Linux-x86_64.sh
```

Now, create a new virtual environment with .theanorc, which device = gpu, it is for Theano 0.8.2 and Lasagne 0.1.
```
$ virtualenv --no-site-packages env01 --python=python2.7
$ cd env01
$ ./env01.sh
```
Install powerful python library, [Pylearn2](https://github.com/lisa-lab/pylearn2): a machine learning research library.
```
git clone git://github.com/lisa-lab/pylearn2
cd pylearn2
python setup.py develop
```
Install powerful python framework, [Arcade Learning Environment](https://github.com/mgbellemare/Arcade-Learning-Environment), A.L.E.
```
git clone https://github.com/mgbellemare/Arcade-Learning-Environment ALE
cd ALE
cmake -DUSE_SDL=ON -DUSE_RLGLUE=OFF .
make -j4
pip install .
deactivate
```
Create another new virtual environment with .theanorc, which device = cuda* for Theano 0.9.0. Because some projects require pygpu 0.7.0 or newer, so use "conda install -c conda-forge pygpu" to install pygpu.
```
$ vi ~/.theanorc
[cuda]
root=/usr/local/cuda
[global]
device = cuda*
floatX = float32

$ virtualenv --no-site-packages env02 --python=python2.7
$ cd env02
$ source bin/activate
$ ./env02.sh
```
Insall Theano 0.9.0
```
$ git clone git://github.com/Theano/Theano.git
$ cd Theano
$ pip install .
```
Install libgpuarray and pygpu at ~/.local. Be sure to install it at ~/.local!
```
$ git clone https://github.com/Theano/libgpuarray.git
$ cd libgpuarray
$ mkdir Build && cd Build
$ cmake .. -DCMAKE_INSTALL_PREFIX=~/.local -DCMAKE_BUILD_TYPE=Release
$ make
$ make install
$ deactivate
```
Add library path to ~/.bashrc.
```
$ vi ~/.bashrc
export CPATH=$CPATH:~/.local/include
export LIBRARY_PATH=$LIBRARY_PATH:~/.local/lib
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:~/.local/lib

$ source ~/.bashrc
```
Go back to env02.
```
$ cd ~/env02
$ source bin/activate
$ cd ~/.local/libgpuarray
$ python setup.py build
$ python setup.py install
$ reboot
```
Test pygpu with the command "python -c "import pygpu; pygpu.test()". If there are some error says "RuntimeError: No test device specified.  Specify one using the DEVICE or GPUARRAY_TEST_DEVICE environment variables.", then run the command with "DEVICE=cuda0 python -c "import pygpu; pygpu.test()".
The test function will test all pygpu function, and then output witch function is not work.
```
$ python -c "import pygpu; pygpu.test()"
```
Install Lasagne, and update is and Theano.
```
$ pip install theano==0.8.2
$ pip install Lasagne==0.1

$ pip install --upgrade --no-deps git+git://github.com/Theano/Theano.git
$ pip install --upgrade https://github.com/Lasagne/Lasagne/archive/master.zip
```
Install powerful python library, [Pylearn2](https://github.com/lisa-lab/pylearn2): a machine learning research library.
```
$ git clone git://github.com/lisa-lab/pylearn2
$ cd pylearn2
$ python setup.py develop
```
Install powerful python framework, [Arcade Learning Environment](https://github.com/mgbellemare/Arcade-Learning-Environment), A.L.E.
```
$ git clone https://github.com/mgbellemare/Arcade-Learning-Environment ALE
$ cd ALE
$ cmake -DUSE_SDL=ON -DUSE_RLGLUE=OFF .
$ make -j4
$ pip install .
$ deactivate
```
###### All dependencies are installed, then test it with some theano project.
