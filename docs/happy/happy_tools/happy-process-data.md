# Command-line

```
usage: happy-process-data [-h] -p PIPELINE

Processes data using the specified pipeline ('reader [preprocessor(s)]
writer').

optional arguments:
  -h, --help            show this help message and exit
  -p PIPELINE, --pipeline PIPELINE
                        The processing pipeline: reader [preprocessor(s)]
                        writer, e.g.: happy-reader -b INPUT_DIR wavelength-
                        subset -f 60 -t 189 sni happy-writer -b OUTPUT_DIR
                        (default: None)
```
