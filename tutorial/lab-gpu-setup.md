#  Available libraries
Library | Directory
--- | ---
cuda & cudnn | /usr/local/cuda-8.0/lib64
libcupti | /usr/local/cuda-8.0/extras/CUPTI/lib64
Anaconda 2 | /usr/local/anaconda2
Intel MKL | /opt/intel/mkl
    
#  Create new user 
## On Ubuntu 16.04 LTS
``` 
sudo adduser <your-username> --ingroup student
```
## On CentOS 7
``` 
sudo adduser <your-username> --gid student
```
#  Clone python environment

```
cd $HOME
```
### For python 2.7
``` 
conda create --name py27 python=2.7
source activate py27
```
### For python 3.5
``` 
conda create --name py35 python=3.5
source activate py35
```


# Mount JAIST Storage

JAIST provides a huge storage capacity (about hundred of Terabytes) on their server and luckily we can mount it on our server. Therefore your data is unified among JAIST clusters and any computers in laboratory 's servers. In order to mount, please consult Viet-san or Vu-san to set up.

Then, assume your mount point is ``/home/some-account/jaist``:
```
mount /home/some-account/jaist
```

