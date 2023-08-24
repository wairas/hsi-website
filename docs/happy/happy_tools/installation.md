# Prerequisites

**Windows:** install `Ubuntu 2022.04.x` from the Microsoft store 
(requires up-to-date WSL2 on Windows 10 Build 19044+ or Windows 11).

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
