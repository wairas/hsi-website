# Command-line

```
usage: happy-process-data reader [preprocessor(s)] writer [-h|--help|--help-all|--help-plugin NAME] 
       [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Processes data using the specified pipeline.

readers: envi-reader, happy-reader, matlab-reader
preprocessors: crop, derivative, divide-annotation-avg, down-sample, extract-regions, multi-pp, pca, pad, pass-through, snv, sni, std-scaler, subtract-annotation-avg, subtract, wavelength-subset
writers: envi-writer, happy-writer, image-writer, matlab-writer, png-writer

optional arguments:
  -h, --help            show this help message and exit
  --help-all            show the help for all plugins and exit
  --help-plugin NAME    show the help for plugin NAME and exit
  -i [INPUT [INPUT ...]], --input [INPUT [INPUT ...]]
                        Optional path to the file(s) to process in batch mode;
                        glob syntax is supported (default: None)
  -I [INPUT_LIST [INPUT_LIST ...]], --input_list [INPUT_LIST [INPUT_LIST ...]]
                        Optional path to the text file(s) listing the files to
                        process in batch mode (default: None)
  -e REGEXP, --exclude REGEXP
                        Regular expression for excluding files from batch processing;
                        gets applied to full file path
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```

## Examples

### HappyData directory to Matlab

The following converts all samples in HappyData format in the `/some/where/happy`
directory to Matlab, storing them in `/some/where/matlab`: 

```bash
happy-process-data \
  -V INFO \
  happy-reader \
    -V INFO \
    -b /some/where/happy \
  matlab-writer \
    -V INFO \
    -b /some/where/matlab
```

### ENVI files to JPG (batch processing)

The following command finds all `.hdr` files recursively below the directory
`/some/where/envi`, turns them into JPEG images and stores them in `/some/where/jpg`:  

```bash
happy-process-data \
  -V INFO \
  -i "/some/where/envi/**/*.hdr" \
  --exclude ".*DARKREF_.*" ".*MASK_.*" \
  envi-reader \
    -V INFO \
    -b . \
    --exclude "DARKREF_.*" "MASK_.*" \
  image-writer \
    -V INFO \
    -b /some/where/jpg \
    -R 95 \
    -G 152 \
    -B 111 \
    -o "{BASEDIR}/{SAMPLEID}.jpg" \
    --suppress_metadata
```
