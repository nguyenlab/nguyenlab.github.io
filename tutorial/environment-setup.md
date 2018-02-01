#  Available libraries
Library | Directory
--- | ---
cuda | /usr/local/cuda-8.0/
cudnn 5.1 | /usr/local/cudnn/cudnnv5.1/
cudnn 6 | /usr/local/cudnn/cudnnv6/
cudnn 7 | /usr/local/cudnn/cudnnv6/
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
Activate the environment when you want to use it.
```
source activate py27
```

### For python 3.5
``` 
cd $HOME
conda create --name py35 python=3.5
```
Activate the environment when you want to use it.
```
source activate py35
```

# Mount JAIST Storage

JAIST provides a huge storage capacity (about hundred of Terabytes) on their server and luckily we can mount it on our server. Therefore your data is unified among JAIST clusters and any computers in laboratory 's servers. In order to mount, please consult Viet-san or Vu-san to set up.

Mount the JAIST directory into your ``$HOME/jaist`` using the password of your JAIST email.
```
mount ~/jaist
```

# Mount JAIST Cluster /work directory
```
sshfs <student-id>@<cluster-name>:/work/your-directory <mount-point>
```
Example:
```
sshfs s161xxxx@uv:/work/s161xxxx /home/your-account/uv
```
