
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
