# Command-line

```
usage: happy-process-data reader [preprocessor(s)] writer [-h|--help|--help-all|--help-plugin NAME] 
       [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Processes data using the specified pipeline.

readers: happy-reader, matlab-reader
preprocessors: crop, derivative, down-sample, extract-regions, multi-pp, pca, pad, pass-through, snv, sni, std-scaler, wavelength-subset
writers: happy-writer, matlab-writer, png-writer

optional arguments:
  -h, --help            show this help message and exit
  --help-all            show the help for all plugins and exit
  --help-plugin NAME    show the help for plugin NAME and exit
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
