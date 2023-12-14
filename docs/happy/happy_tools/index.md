[happy-tools](https://github.com/wairas/happy-tools) contains several command-line 
utilities and graphical viewers for HSI files:

* [happy-data-viewer](happy-data-viewer.md) - for viewing HAPPy data folders
* [happy-envi-viewer](happy-envi-viewer.md) - for viewing ENVI HSI images
* [happy-generate-image-regions-objects](happy-generate-image-regions-objects.md) - generates datasets as numpy cubes for deep learning
* [happy-hdr-info](happy-hdr-info.md) - outputs information on ENVI HDR files
* [happy-hsi2rbg](happy-hsi2rbg.md) - generates fake RGB PNG files from HSI images
* [happy-mat-info](happy-mat-info.md) - outputs Matlab struct information
* [happy-opex2happy](happy-opex2happy.md) - converts OPEX JSON annotations and PNG images into happy data structures
* [happy-opex-labels](happy-opex-labels.md) - performs actions on OPEX JSON files that it located
* [happy-plot-preproc](happy-plot-preproc.md) - plots set of pixels using various preprocessors
* [happy-process-data](happy-process-data.md) - applies a preprocessing pipeline to the data
* [happy-raw-check](happy-raw-check.md) - sanity checks on raw capture folders
* [happy-scikit-regression-build](happy-scikit-regression-build.md) - evaluates regression models on HAPPy data
* [happy-scikit-segmentation-build](happy-scikit-segmentation-build.md) - evaluates segmentation models on HAPPy data
* [happy-scikit-unsupervised-build](happy-scikit-unsupervised-build.md) - evaluates cluster models on HAPPy data
* [happy-splitter](happy-splitter.md) - for generating train/validation/test splits for HAPPy data

These tools are available from the Python virtual environment that they were
installed. E.g., when following the installation instructions on this website,
the tools would be located in the following directory in the user's home folder:

```bash
happy/bin
```

Overview of available plugins and their respective parameters is located here:

[https://github.com/wairas/happy-tools/blob/main/plugins/README.md](https://github.com/wairas/happy-tools/blob/main/plugins/README.md)
