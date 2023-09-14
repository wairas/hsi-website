# Prerequisites

* Linux (Ubuntu/Debian)

    * Docker (`sudo apt install docker.io`) 
    * redis-server (`sudo apt install redis-server`)
    * wget (`sudo apt install wget`)

* [Windows/WSL2](wsl2.md)
  
    * Ubuntu 22.04.x from the Microsoft store
    * [Docker](https://www.data-mining.co.nz/applied-deep-learning/windows/)
    * redis-server (`sudo apt install redis-server`)
    * wget (`sudo apt install wget`)

# Installation

Go to your home directory:
  
```bash
cd ~
```

Download the [happy-setup.sh](https://github.com/wairas/happy-scripts/blob/main/happy-setup.sh) 
script and make it executable:


```bash
wget -O happy-setup.sh https://raw.githubusercontent.com/wairas/happy-scripts/main/happy-setup.sh
chmod a+x happy-setup.sh 
```

Execute the script:

```bash
./happy-setup.sh
```

Minimal installation items to execute:

* `Prepare system` (ensures that all required system libraries are present)
* `Install Happy Tools`
* `Install SAM-HQ` (or if you prefer, `Install SAM`)
  
**Notes:**

* `SAM` and `SAM-HQ` can be installed in parallel, but only one of them can 
  actively running, as they both use the same redis channels for communication
  (that way they are interchangeable).
* [ADAMS](adams.md) can be used for annotating objects in your scanned images.
