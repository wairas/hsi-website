Facebook's [Segment Anything](https://ai.facebook.com/research/publications/segment-anything/)
are pretrained models that perform image segmentation on RGB images and can aid
the human in the annotation process.

# Prerequisites

## Linux

* docker
* redis-server (`sudo apt install redis-server`)
  
## Windows
* WSL2 using Ubuntu 20.04 or 22.04
  * docker ([instructions](https://www.data-mining.co.nz/applied-deep-learning/windows/))
  * redis-server (`sudo apt install redis-server`)

## Directories
  
```
sam
|
+-- cache    # cache directory for Pytorch-related files 
|
+-- models   # for storing the  
```

You can create the structure using the following command:
  
```bash
mkdir -p sam/cache \
mkdir -p sam/models 
```

## Pretrained models

Pretrained models can be downloaded from [here](https://github.com/facebookresearch/segment-anything),
with the medium-sized [vit_l](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_l_0b3195.pth) 
being the recommended one (requires <6GB GPU RAM). `vit_l` is used in the commands below.

## Launching Docker and Redis under WLS2 (without Docker Desktop UI)
    
* Create a bash script `happy_sam_start.sh` in `/usr/local/bin` with the following content:
    
```bash
#!/bin/bash
redis-server &
dockerd &
seq 10 | xargs -I{} sh -c "echo waiting...; sleep 1;"
```
    
* Make the script executable with `sudo chmod a+x happy_sam_start.sh`

* Create a bash script `happy_sam_stop.sh` in `/usr/local/bin` with the following content:

```bash
#!/bin/bash
killall redis-server
killall dockerd
```
    
* Make the script executable with `sudo chmod a+x happy_sam_stop.sh`


# Launching Docker and Redis under WLS2 (without Docker Desktop UI)

```bash
sudo /usr/local/bin/happy_sam_start.sh
```

Wait till the `Waiting...` output stops, which waits for about 10 seconds
after the Docker daemon starts in the background.


# Launching SAM

In a terminal, run the following command from within the `sam` directory to
launch the SAM model (which communicates via the `sam_in` and `sam_out`
Redis channels):

```bash
docker run --pull always --rm \
  -u $(id -u):$(id -g) -e USER=$USER \
  -v `pwd`/cache:/.cache -v `pwd`:/workspace \
  --gpus=all --net=host \
  -t waikatodatamining/pytorch-sam:2023-04-16_cuda11.6 \
  sam_predict_redis \
  --redis_in sam_in \
  --redis_out sam_out \
  --model /workspace/models/sam_vit_l_0b3195.pth \
  --model_type vit_l \
  --verbose
```

# Stopping SAM

Find the process ID (PID) of the Python process for SAM and use `kill -9 PID`.


# Stopping Docker and Redis under WLS2 (without Docker Desktop UI)

```bash
sudo /usr/bin/happy_sam_stop.sh
```

**NB:** This will also stop any running SAM process. 
