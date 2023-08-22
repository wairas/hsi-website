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

Install the happy-tools straight from the repository:

```bash
./happy/bin/pip install git+https://github.com/wairas/happy-tools.git
```

# Updating

Once installed, you can update the library as follows:

```bash
./happy/bin/pip uninstall happy-tools
./happy/bin/pip install git+https://github.com/wairas/happy-tools.git
```


# Tools

The following tools are available (located in `./happy/bin`):

* `envi-viewer` - for viewing ENVI HSI images
* `happy-hsi2csv` - converts HSI images into CSV
* `happy-hsi2rbg` - generates fake RGB PNG files from HSI images
