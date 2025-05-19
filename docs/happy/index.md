# Overview

<p align="center">
  <img src="img/logo.png" alt="HAPPy logo">
</p>

HAPPy, short for *Hyperspectral Application Platform in Python*, stands as a pioneering platform at the forefront of hyperspectral imaging technology. Designed by the Hyperspectral Imaging Group at the University of Waikato, HAPPy unifies hyperspectral workflows for how hyperspectral images are acquired, processed, and analyzed.

At its core, HAPPy seamlessly integrates data acquisition, annotation, analysis, and the exploration of novel statistical machine learning and deep learning approaches. 

# Key Features

Containerized Algorithm Management: HAPPy simplifies algorithm deployment, ensuring compatibility with open-source machine learning platforms.

Hardware-Software Calibration Protocols: Real-time machine learning model assessment at the imaging front enhances adaptability.

Efficiency in Hyperspectral Workflow: Accelerated experimentation allows quick feasibility assessment and method shortlisting for development.

Empowering Innovation: HAPPy empowers researchers to bridge the gap between hyperspectral data and state-of-the-art machine learning algorithms. It is the tool that fosters quicker experimentation, innovation, and discovery within the dynamic field of hyperspectral imaging.

Open Source and Collaborative: Committed to the principles of open-source collaboration, we invite researchers, engineers, and enthusiasts from around the world to explore, contribute, and leverage the HAPPy. 

Get Started:
Whether you are a seasoned hyperspectral imaging expert or just embarking on your journey, HAPPy is here to simplify, accelerate, and amplify your research efforts. Scroll down for information on installation and usage, as well as access to our tools and publications.

# Installation

The tools have been tested on Linux (Ubuntu/Debian) and under Windows with 
WSL2 using Ubuntu 22.04.x.

* [Notes on WSL2](wsl2.md)
* [Installing the tools](installation.md)

# Usage

Once installed using the above instructions, you can launch graphical tools
and Docker images (start/stop) using the `happy-launch.sh` script from your 
home directory:

```bash
./happy-launch.sh
```

# Tools

More details on the tools that are available through the HAPPy project can
be found on the respective tool pages:

* [ADAMS](adams.md)
* [happy-tools](happy_tools/index.md)
* [Segment Anything](sam.md)
* [Segment Anything in High Quality](sam-hq.md)

**NB:** These pages also contain detailed instructions on how to install them, 
which you can ignore if you used the `happy-setup.sh` installation script.


# Docker

For available Docker images, please see the [Docker](docker.md) page.
