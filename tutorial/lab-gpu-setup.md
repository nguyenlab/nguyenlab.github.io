#  Available libraries
Library | Directory
--- | ---
cuda | /usr/local/cuda-8.0/lib64
cudnn | /usr/local/cudnn/cudnnv5.1/lib64
libcupti | /usr/local/cuda-8.0/extras/CUPTI/lib64
Anaconda 2 | /usr/local/anaconda2
Intel MKL | /opt/intel/mkl
    
#  Create new user 
``Note:`` This part requires admin privileges
## On Ubuntu 16.04 LTS
``` 
sudo adduser <your-username> --ingroup student
```
## On CentOS 7
``` 
sudo adduser <your-username> --gid student
```
#  Clone python environment

### For python 2.7
``` 
cd $HOME
conda create --name py27 python=2.7
```
Then append following line to the ``~/.bashrc`` file before logging out and re-logging in:
```
export PATH=$HOME/.conda/envs/py27/bin/:$PATH
```

### For python 3.5
``` 
cd $HOME
conda create --name py35 python=3.5
```
Then append following line to the ``~/.bashrc`` file before logging out and re-logging in:
```
export PATH=$HOME/.conda/envs/py35/bin/:$PATH
```


# Mount JAIST Storage

JAIST provides a huge storage capacity (about hundred of Terabytes) on their server and luckily we can mount it on our server. Therefore your data is unified among JAIST clusters and any computers in laboratory 's servers. In order to mount, please consult Viet-san or Vu-san to set up.

Then, assume your mount point is ``/home/some-account/jaist``, simply run following command:
```
mount /home/some-account/jaist
```

# Mount JAIST Cluster /work directory
```
sshfs <student-id>@<cluster-name>:/work/your-directory <mount-point>
```
Example:
```
sshfs s161xxxx@uv:/work/s161xxxx /home/your-account/uv
```

# Manipulate multiple GPUs
There are 4 GPUS in our server, they are indexed differently by two systems. One is the ``nvidia-smi`` command, other is the operating system through a variable named ``CUDA_VISIBLE_DEVICES``. Here are the mapping table among these two systems:

Nvidia Management Interface (nvidia-smi) | Operating System ($CUDA_VISIBLE_DEVICES)
--- | ---
0 | 3
1 | 2
2 | 1
3 | 0

- Check non-used GPUs, using the Nvidia-provided management interface:
```
nvidia-smi
```

- To run on a single GPU, set the $CUDA_VISIBLE_DEVICES with the index of the GPU, example: 
```
export CUDA_VISIBLE_DEVICES="1"
```

- To run on multiple GPUs,  set the $CUDA_VISIBLE_DEVICES with the indexs of the GPUs (separated by comma), example:
```
export CUDA_VISIBLE_DEVICES="2,3"
```
