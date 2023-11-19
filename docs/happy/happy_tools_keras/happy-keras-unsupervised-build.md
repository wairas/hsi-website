# Command-line

```
usage: happy-keras-unsupervised-build [-h] -d DATA_FOLDER [-P PREPROCESSORS]
                                      -t TARGET [-n NUM_CLUSTERS] -s
                                      HAPPY_SPLITTER_FILE -o OUTPUT_FOLDER

Build a Keras-based unsupervised segmentation model.

optional arguments:
  -h, --help            show this help message and exit
  -d DATA_FOLDER, --data_folder DATA_FOLDER
                        Path to the data folder (default: None)
  -P PREPROCESSORS, --preprocessors PREPROCESSORS
                        The preprocessors to apply to the data. Either
                        preprocessor command-line(s) or file with one
                        preprocessor command-line per line. (default:
                        wavelength-subset -f 60 -t 189 snv derivative pad -W
                        128 -H 128 -v 0)
  -t TARGET, --target TARGET
                        Name of the target variable (default: None)
  -n NUM_CLUSTERS, --num_clusters NUM_CLUSTERS
                        The number of clusters to use (default: 4)
  -s HAPPY_SPLITTER_FILE, --happy_splitter_file HAPPY_SPLITTER_FILE
                        Path to JSON file containing splits (default: None)
  -o OUTPUT_FOLDER, --output_folder OUTPUT_FOLDER
                        Path to the output folder (default: None)
```
