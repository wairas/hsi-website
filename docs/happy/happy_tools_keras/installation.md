# Prerequisites

* [Windows/WSL](../wsl2.md): `Ubuntu 2022.04.x` from the Microsoft store
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
./happy/bin/pip install git+https://github.com/wairas/happy-tools-keras.git
```

# Updating

Once installed, you can update the library as follows:

```bash
./happy/bin/pip uninstall -y happy-tools happy-tools-keras
./happy/bin/pip install git+https://github.com/wairas/happy-tools.git
./happy/bin/pip install git+https://github.com/wairas/happy-tools-keras.git
```

# Uninstall

You can completely remove the tools by simply deleting the `happy` directory:

```bash
rm -Rf ./happy
```
