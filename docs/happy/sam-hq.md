[Segment Anything in High Quality](https://github.com/SysCV/sam-hq) (SAM-HQ) works
like [SAM](sam.md) and consists of pretrained models that perform image 
segmentation on RGB images and can aid the human in the annotation process.

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
sam-hq
|
+-- cache    # cache directory for Pytorch-related files 
|
+-- models   # for storing the SAM-HQ models
```

You can create the structure using the following command:
  
```bash
mkdir -p sam-hq/cache \
mkdir -p sam-hq/models 
```

## Pretrained models

Pretrained models can be downloaded from [here](https://huggingface.co/lkeab/hq-sam/tree/main),
with the medium-sized [vit_l](https://huggingface.co/lkeab/hq-sam/resolve/main/sam_hq_vit_l.pth) 
being the recommended one (requires <6GB GPU RAM). `vit_l` is used in the commands below.

From within the `sam-hq/models` directory, run the following command:

```bash
wget https://huggingface.co/lkeab/hq-sam/resolve/main/sam_hq_vit_l.pth
```

## Service scripts (WSL2 without Docker Desktop UI)
  
* Create a bash script `happy_samhq_start.sh` in `/usr/local/bin` with the following content:
    
```bash
#!/bin/bash
redis-server &
dockerd &
seq 10 | xargs -I{} sh -c "echo waiting...; sleep 1;"
```
    
* Make the script executable with `sudo chmod a+x happy_samhq_start.sh`

* Create a bash script `happy_samhq_stop.sh` in `/usr/local/bin` with the following content:

```bash
#!/bin/bash
killall redis-server
killall dockerd
```
    
* Make the script executable with `sudo chmod a+x happyhq_sam_stop.sh`

## SAM scripts

In the `sam-hq` directory, create script `start.sh` with the following content:

```bash
#!/bin/bash

scriptdir=`dirname -- "$0";`

docker run --pull always --rm \
  -u $(id -u):$(id -g) -e USER=$USER \
  -v $scriptdir/cache:/.cache \
  -v $scriptdir:/workspace \
  --gpus=all --net=host \
  -t waikatodatamining/pytorch-sam-hq:2023-08-17_cuda11.6 \
  samhq_predict_redis \
  --redis_in sam_in \
  --redis_out sam_out \
  --model /workspace/models/sam_hq_vit_l.pth \
  --model_type vit_l \
  --verbose
```

And make executable with `chmod a+x start.sh`.

**NB:** This script uses the `sam_in` and `sam_out` Redis channels to make
it a drop-in replacement for [SAM](sam.md) in the [envi-viewer](./happy_tools/envi-viewer.md).

Next, create a script called `stop.sh` with the following content:

```bash
#!/bin/bash

ids=`ps a | grep [s]amhq_predict_redis | sed s/"^[ ]*"//g | cut -f1 -d" "`
for id in $ids
do
  kill -9 $id
done
```

And make executable with `chmod a+x stop.sh`.


# Starting

## Docker and Redis (WSL2 without Docker Desktop UI)

```bash
sudo /usr/local/bin/happy_samhq_start.sh
```

Wait till the `Waiting...` output stops, which waits for about 10 seconds
after the Docker daemon starts in the background.

## SAM

In the `sam-hq` directory, execute the `start.sh` script.

# Stopping

## SAM

In the `sam-hq` directory, execute the `stop.sh` script.

## Docker and Redis (WSL2 without Docker Desktop UI)

```bash
sudo /usr/local/bin/happy_samhq_stop.sh
```

**NB:** This will also stop any running SAM/SAM-HQ process. 
