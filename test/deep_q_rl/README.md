# deep_q_rl
This package provides a Lasagne/Theano-based implementation of the deep Q-learning algorithm. Download rom file from [here](http://www.atariage.com/system_items.html?SystemID=2600&ItemTypeID=ROM), then rename it to breakout.in and put it under the folder roms.

```
$ git clone https://github.com/spragunr/deep_q_rl.git
$ sudo ./dep_script.sh
$ cd deep_q_rl
```
The `run_nips.py` script should take 2-4 days to complete.
```
$ ./run_nips.py --rom breakout
```
The `run_nature.py` script will take 6-10 days to finish training.
```
$ ./run_nature.py --rom breakout