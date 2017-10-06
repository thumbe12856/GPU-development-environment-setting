# Lasagne MNIST
This is a little test for handwriting identification from 0 to 9 with Theano and Lasagne.
```
$ git clone https://github.com/Lasagne/Lasagne.git
$ cd Lasagne/examples
$ python minst.py
```

# Result
1. ```pygpu: 0.7.3, Theano: 0.10.0b3+126.g8dccbe6```  
(1) Result:
- 0.25 sec for every epoch
![GTX1060-pygpu=0.7.3-minst-device=cuda0.png](https://raw.githubusercontent.com/thumbe12856/GPU-development-environment-setting/master/pictures/GTX1060-pygpu=0.7.3-minst-device=cuda0.png)

Equipment:
- GTX1060 6GB
- DEVICE = cuda0

(2) Result:
- 0.516 sec for every epoch
![GTX1060-minst-device=cuda0.png](https://raw.githubusercontent.com/thumbe12856/GPU-development-environment-setting/master/pictures/GTX1060-minst-device=cuda0.png)

Equipment:
- GTX750Ti 2GB
- DEVICE = cuda0

2. ```pygpu version = 0.6.9, , Theano: 0.9.0```  
(1)
Result:
- 0.53 sec for every epoch
![GTX750Ti-pygpu=0.6.9-minst-device=cuda0.png](https://raw.githubusercontent.com/thumbe12856/GPU-development-environment-setting/master/pictures/GTX750Ti-pygpu=0.6.9-minst-device=cuda0.png)

Equipment:
- GTX750Ti 2GB
- DEVICE = cuda0


(2)
Result:
- 0.85 sec for every epoch
![GTX750Ti-pygpu=0.6.9-minst-device=gpu](https://raw.githubusercontent.com/thumbe12856/GPU-development-environment-setting/master/pictures/GTX750Ti-pygpu=0.6.9-minst-device=gpu.png)

Equipment:
- GTX750Ti 2GB
- DEVICE = gpu
