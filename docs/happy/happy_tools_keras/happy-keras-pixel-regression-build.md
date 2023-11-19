# Command-line

```
usage: happy-keras-pixel-regression-build [-h] -d DATA_FOLDER
                                          [-P PREPROCESSORS] -t TARGET -s
                                          HAPPY_SPLITTER_FILE -o OUTPUT_FOLDER

Evaluate a Keras-based pixel regression model.

optional arguments:
  -h, --help            show this help message and exit
  -d DATA_FOLDER, --data_folder DATA_FOLDER
                        Path to the data folder (default: None)
  -P PREPROCESSORS, --preprocessors PREPROCESSORS
                        The preprocessors to apply to the data. Either
                        preprocessor command-line(s) or file with one
                        preprocessor command-line per line. (default: crop -W
                        320 -H 648 wavelength-subset -f 60 -t 189 sni snv
                        derivative -w 15 -d 1 pad -W 320 -H 648 -v 0 down-
                        sample)
  -t TARGET, --target TARGET
                        Name of the target variable (default: None)
  -s HAPPY_SPLITTER_FILE, --happy_splitter_file HAPPY_SPLITTER_FILE
                        Path to JSON file containing splits (default: None)
  -o OUTPUT_FOLDER, --output_folder OUTPUT_FOLDER
                        Path to the output folder (default: None)
```
