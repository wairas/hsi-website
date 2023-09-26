# Command-line

```
usage: happy-scikit-unsupervised-build [-h] -d DATA_FOLDER
                                       [-m CLUSTERER_METHOD]
                                       [-p CLUSTERER_PARAMS] -s
                                       HAPPY_SPLITTER_FILE -o OUTPUT_FOLDER
                                       [-r REPEAT_NUM]

Evaluate clustering on hyperspectral data using specified clusterer and pixel
selector.

optional arguments:
  -h, --help            show this help message and exit
  -d DATA_FOLDER, --data_folder DATA_FOLDER
                        Directory containing the hyperspectral data (default:
                        None)
  -m CLUSTERER_METHOD, --clusterer_method CLUSTERER_METHOD
                        Clusterer name (e.g.,
                        kmeans,agglomerative,spectral,dbscan,meanshift) or
                        full class name (default: kmeans)
  -p CLUSTERER_PARAMS, --clusterer_params CLUSTERER_PARAMS
                        JSON string containing clusterer parameters (default:
                        {})
  -s HAPPY_SPLITTER_FILE, --happy_splitter_file HAPPY_SPLITTER_FILE
                        Happy Splitter file (default: None)
  -o OUTPUT_FOLDER, --output_folder OUTPUT_FOLDER
                        Output JSON file to store the predictions (default:
                        None)
  -r REPEAT_NUM, --repeat_num REPEAT_NUM
                        Repeat number (default: 0) (default: 0)
```
