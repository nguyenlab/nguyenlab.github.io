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

JAIST provides a huge storage capacity (about hundred of Terabytes) on their server and luckily we can mount it on our server. Therefore your data is unified among JAIST clusters and any computers in laboratory 's servers. In order to mount, you at least need following seeds:
- Student ID and JAIST mail password are needed (ofcourse, it is yours)
- The sudo account named "nguyenlab" and its password (please ask Viet-san or Vu-san directly if you need)
- Your own account on lab computer and its password (the one you have just created in previous section)

Please perform step by step:

## Identify storage path
First using SSH login to JAIST high performance computer such as HPCC, UV and run following command:

``` 
mount | grep <your-student-id>
```
The output may look like these patterns:

```
fs003:/volumes/vol03/fs0035/s1510xxx on /home/s1510xxx
150.65.xxx.xxx:/ifs/home/s1604/s1610xxx on /home/s1610xxx
```
Look at the directory, you can see ``s1604`` and ``fs0035`` is the hostname of the storage server. So the ``storage path`` of your directory should be: 

```
//<storage-hostname>.jaist.ac.jp/<storage-hostname>/<your-student-id>/
```

Example:

```
//s1605.jaist.ac.jp/s1604/s1610xxx/
```

## Obtain the user id (uid) on lab's computer & create mount point
Secondly, user ID is a 4-character integer number. To check the user id on linux system, login to lab's computer using your own account and run following command and capture the "uid" value

``` 
id | grep uid
```
Then create a mount point directory:
```
mkdir $HOME/jaist
```

## Mount 

Finally, login lab's computer using ``nguyenlab`` account and mount JAIST drive on lab's server

``` 
sudo mount -t cifs -o username=<your-studen-id>,password=<your-jaist-mail-password>,uid=<the-user-id-in-prev-step> <storage-path> ~/jaist
```

Example:

``` 
sudo mount -t cifs -o username=s1610xxx,password=<my-secret-password>,uid=10xx //s1605.jaist.ac.jp/s1605/s1610xxx /home/my_account/jaist
```
