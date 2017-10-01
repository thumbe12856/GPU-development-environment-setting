# Q-Optimality-Tightening
Running the project may cost few days. It is ShibiHe's implementation to paper [Learning to Play in a Day: Faster Deep Reinforcement Learning by Optimality Tightening](https://openreview.net/pdf?id=rJ8Je4clg).

```
$ git clone https://github.com/ShibiHe/Q-Optimality-Tightening.git
$ pip install matplotlib    # Python 2D plotting library    
$ pip install pillow        # for scipy.misc import imread

$ cd code
$ THEANO_FLAGS='deivce=cuda0, allow_gc=False' python run_OT.py -r frostbite --close2
```