## NeRF DDP Implementation

nerf_ddp.py is a pytorch DDP example. You can simply copy it to your local, or git clone this repo. 

### Dependency

a. virtual environment

```angular2html
mkdir venv
virtualenv -p python3.7 venv
source venv/bin/activate
```

b.  requirements
```angular2html
pip install -r requirements.txt
```


** Before launching, make sure to change the line #1020 `[MASTER_ADDR]` to your master IP address

** To adjust the number of iterations, go to the line #64 `n_iters` and change it accordingly. 


### Launch multiple (two) nodes with multiple GPUS

Assume there are `2` nodes and each with `8` gpus. On each node, launch the following commands separately

```
python nerf_ddp.py -n 2 -g 8,8 -i 0
python nerf_ddp.py -n 2 -g 8,8 -i 1
```
