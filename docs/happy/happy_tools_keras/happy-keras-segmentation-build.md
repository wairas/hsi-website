# Command-line

```
usage: happy-keras-segmentation-build [-h] -d DATA_FOLDER -t TARGET
                                      [-n NUM_CLASSES] -s HAPPY_SPLITTER_FILE
                                      -o OUTPUT_FOLDER

Build a Keras-based pixel segmentation model.

optional arguments:
  -h, --help            show this help message and exit
  -d DATA_FOLDER, --data_folder DATA_FOLDER
                        Path to the data folder (default: None)
  -t TARGET, --target TARGET
                        Name of the target variable (default: None)
  -n NUM_CLASSES, --num_classes NUM_CLASSES
                        The number of classes, used for generating the mapping
                        (default: 4)
  -s HAPPY_SPLITTER_FILE, --happy_splitter_file HAPPY_SPLITTER_FILE
                        Path to JSON file containing splits (default: None)
  -o OUTPUT_FOLDER, --output_folder OUTPUT_FOLDER
                        Path to the output folder (default: None)
```
