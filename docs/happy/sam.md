Facebook's [Segment Anything](https://ai.facebook.com/research/publications/segment-anything/) (SAM)
are pretrained models that perform image segmentation on RGB images and can aid
the human in the annotation process.

# Prerequisites

## Linux

* docker
* redis-server (`sudo apt install redis-server`)
  
## Windows

* [WSL2](wsl2.md) using 22.04.x
  
    * docker ([instructions](https://www.data-mining.co.nz/applied-deep-learning/windows/))
    * redis-server (`sudo apt install redis-server`)

## Directories
  
```
sam
|
+-- cache    # cache directory for Pytorch-related files 
|
+-- models   # for storing the SAM models
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

From within the `sam/models` directory, run the following command:

```bash
wget https://dl.fbaipublicfiles.com/segment_anything/sam_vit_l_0b3195.pth
```

## Service scripts (WSL2 without Docker Desktop UI)
  
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

## SAM scripts

In the `sam` directory, create script `start.sh` with the following content:

```bash
#!/bin/bash

scriptdir=`dirname -- "$0";`

docker run --pull always --rm \
  -u $(id -u):$(id -g) -e USER=$USER \
  -v $scriptdir/cache:/.cache \
  -v $scriptdir:/workspace \
  --gpus=all --net=host \
  -t waikatodatamining/pytorch-sam:2023-04-16_cuda11.6 \
  sam_predict_redis \
  --redis_in sam_in \
  --redis_out sam_out \
  --model /workspace/models/sam_vit_l_0b3195.pth \
  --model_type vit_l \
  --verbose
```

And make executable with `chmod a+x start.sh`.

Next, create a script called `stop.sh` with the following content:

```bash
#!/bin/bash

ids=`ps a | grep [s]am_predict_redis | sed s/"^[ ]*"//g | cut -f1 -d" "`
for id in $ids
do
  kill -9 $id
done
```

And make executable with `chmod a+x stop.sh`.


# Starting

## Docker and Redis (WSL2 without Docker Desktop UI)

```bash
sudo /usr/local/bin/happy_sam_start.sh
```

Wait till the `Waiting...` output stops, which waits for about 10 seconds
after the Docker daemon starts in the background.

## SAM

In the `sam` directory, execute the `start.sh` script.

# Stopping

## SAM

In the `sam` directory, execute the `stop.sh` script.

## Docker and Redis (WSL2 without Docker Desktop UI)

```bash
sudo /usr/local/bin/happy_sam_stop.sh
```

**NB:** This will also stop any running SAM/SAM-HQ process. 
