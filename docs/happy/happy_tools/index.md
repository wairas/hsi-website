[happy-tools](https://github.com/wairas/happy-tools) contains several command-line 
utilities:

* [happy-generate-image-regions-objects](happy-generate-image-regions-objects.md) - generates datasets as numpy cubes for deep learning
* [happy-hdr-info](happy-hdr-info.md) - outputs information on ENVI HDR files
* [happy-hsi2rbg](happy-hsi2rbg.md) - generates fake RGB PNG files from HSI images
* [happy-mat-info](happy-mat-info.md) - outputs Matlab struct information
* [happy-ann2happy](happy-ann2happy) - converts OPEX JSON polygon, ENVI pixel annotations and PNG images into happy data structures
* [happy-opex-labels](happy-opex-labels.md) - performs actions on OPEX JSON files that it located
* [happy-plot-preproc](happy-plot-preproc.md) - plots set of pixels using various preprocessors
* [happy-process-data](happy-process-data.md) - applies a preprocessing pipeline to the data
* [happy-raw-check](happy-raw-check.md) - sanity checks on raw capture folders
* [happy-scikit-regression-build](happy-scikit-regression-build.md) - evaluates regression models on HAPPy data
* [happy-scikit-segmentation-build](happy-scikit-segmentation-build.md) - evaluates segmentation models on HAPPy data
* [happy-scikit-unsupervised-build](happy-scikit-unsupervised-build.md) - evaluates cluster models on HAPPy data
* [happy-splitter](happy-splitter.md) - for generating train/validation/test splits for HAPPy data
* [happy-sub-images](happy-sub-images.md) - for exporting annotated sub-samples into separate files

Graphical user interface tools using the tkinter widgets have been moved to the 
[happy-tools-tkinter](https://github.com/wairas/happy-tools-tkinter) library.
You can find the documentation on these tools here:

[happy-tools-tkinter](../happy_tools_tkinter/index.md)

Command-line and graphical tools are available from the Python virtual environment 
that they were installed in. E.g., when following the installation instructions on this website,
the tools would be located in the following directory in the user's home folder:

```bash
happy/bin
```

Overview of available plugins and their respective parameters is located here:

[https://github.com/wairas/happy-tools/blob/main/plugins/README.md](https://github.com/wairas/happy-tools/blob/main/plugins/README.md)
