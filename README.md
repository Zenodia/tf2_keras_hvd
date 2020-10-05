# TensorFlow 2.X + Keras + HVD stderr experiment 

## Executive summary - 
This is a reproducible of the question brought up by Veoneer, where they observed when using NGC image nvcr.io/nvidia/tensorflow:20.09-tf2-py3 ( TF2.3) 
the stderr cannot be suppressed ! see below steps to reproduce 

## Requirements -
This experiment was run on NVIDIA DGX with 4 V100 GPU. 

You will need at least the following minimum setup:
- Supported Hardware: NVIDIA GPU with Pascal Architecture or later (Pascal, Volta, Turing)
- Any supported OS for nvidia docker
- [NVIDIA-Docker 2](https://github.com/NVIDIA/nvidia-docker)
- NVIDIA Driver ver. 450.51.06 


## NGC Docker Container used
- TensorFlow 20.09-tf2-py3 NGC container 

## Step 0 - download the repo 
```git clone ssh://git@gitlab-master.nvidia.com:12051/zcharpy/veoneer_question_tf2_keras_hvd.git```
```cd Veoneer_question_tf2_keras_hvd```
or go to this Google Drive link to download the dataset as well as the script for quick reproducibility 
![data and script](https://drive.google.com/drive/folders/13w512EnSVyrfq5D6EKYvW-L03PHvZzXY?usp=sharing)

## Step 1- pull and run the NGC docker image 
``` docker run --gpus '"device=2,3,4,5"' -it --rm -v $(pwd):/workspace nvcr.io/nvidia/tensorflow:20.09-tf2-py3 ```
## Step 2- run the jupyter notebook to see the stderr 
``` exp_tf_keras_hvd_2009.ipynb ```