# Set up environments for using GPUs

## Set up CUDA
CUDA 8 

```
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:$LD_LIBRARY_PATH
```

CUDA 9 (updating)


## Set up CuDNN

CuDNN 5.1 (For pytorch, tensorflow 1.2 and older)

```
export LD_LIBRARY_PATH=/usr/local/cudnn/cudnnv5.1/lib64:$LD_LIBRARY_PATH
```

CuDNN 6 (For tensorflow 1.3, 1.4)
```
export LD_LIBRARY_PATH=//usr/local/cudnn/cudnnv6/lib64:$LD_LIBRARY_PATH
```

CuDNN 7 (For tensorflow 1.5)
```
export LD_LIBRARY_PATH=//usr/local/cudnn/cudnnv7/lib64:$LD_LIBRARY_PATH
```

## Manipulate multiple GPUs
There are 4 GPUs in our server, they are indexed differently by two systems: the ``nvidia-smi`` command and the operating system (through a variable named ``CUDA_VISIBLE_DEVICES``). Here are the mapping table between two systems:

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
