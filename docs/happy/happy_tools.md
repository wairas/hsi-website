[happy-tools](https://github.com/wairas/happy-tools) contains several command-line 
utilities and a graphical viewer for HSI ENVI files.

# Prerequisites

* Python
* Virtual environments

```bash
sudo apt install virtualenv python3-tk
```

# Installation

In the home directory, create a Python virtual environment in directory `happy` 
with access to the system-wide installed libraries:

```bash
virtualenv --system-site-packages -p /usr/bin/python3 happy
```

```bash
./happy/bin/pip install git+https://github.com/wairas/happy-tools.git
```

# Tools

The following tools are available (located in `./happy/bin`):

* `happy-hsi2csv` - converts HSI images into CSV
* `happy-hsi2rbg` - generates fake RGB PNG files from HSI images
* `happy-viewer` - for viewing HSI images
