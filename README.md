# Plant Detection On Railway Tracks Using Neural Networks
## Installation Guide

Following dependencies are required to run the project.

- Anaconda/Miniconda Environment
- PaddleSeg 
- YOLOv5
- Norfair

## Anaconda Installation
To install anaconda refer to www.anaconda.com to download the files.
After successful installation run the following commands to create a conda environment
```console
conda create -n plant_detection python=3.8
conda activate plant_detection
```
Once we are done setting up conda environment, we can move to install dependencies.

## PaddleSeg Installation
To install paddleseg please follow the instructions to install as per hardware i.e. CPU or GPU
First we need to install paddlepaddle as per harware
### 1. For CPU:
```console
python -m pip install paddlepaddle==2.2.2 -i https://pypi.tuna.tsinghua.edu.cn/simple
```
### 2. For GPU:
```console
python -m pip install paddlepaddle-gpu==2.2.2.post101 -f https://www.paddlepaddle.org.cn/whl/linux/mkl/avx/stable.html

```

Run the following script in python shell to check if the installation is successfull.
```
>>> import paddle
>>> paddle.utils.run_check()

# If the following prompt appears on the command line, the PaddlePaddle installation is successful.
# PaddlePaddle is installed successfully! Let's start deep learning with PaddlePaddle now.

# Confirm PaddlePaddle version
>>> print(paddle.__version__)
```

### 3. Install PaddleSeg:
Run the following command to install PaddleSeg
```console
pip install paddleseg
```

## YOLOv5 Installation

To install YOLOv5 and its dependencies, run the following command in the root directory of code
```console
pip install -r requirements.txt
```

## Norfair Installation
To install Norfair run the following command
```console
pip install "norfair[metric]"
```

## Training on RWTH Cluster
### 1. Training BiSeNet V2
To train BiSeNet V2, go to the training directory and run shell script by following commands
```console
cd training/segmentation
sbatch bisenet.sh
```
For the details of **bisenet.sh** file, please refer to the comments in the file. In the file it is important to change the directory to current working directory. The line is amrked IMPORTANT

### 2. Training YOLOv5
To train BiSeNet V2, go to the training directory and run shell script by following commands
```console
cd training/detection
sbatch yolo.sh
```
For the details of **yolo.sh** file, please refer to the comments in the file. In the file it is important to change the directory to current working directory. The line is amrked IMPORTANT


## Inference Vegetation Detection
To infer vegetation detection, go to the inference directory and run inference files by following commands
```console
cd inference
python infer_neural.py
```
Once you execute this file, different parameters can be changed e.g. video path. For parameters details please use following command 
```console
python infer_neural.py -h
```

To infer vegetation detection on Cluster, go to the inference directory and run shell script by following commands
```console
cd inference
python infer_neural.sh
```
