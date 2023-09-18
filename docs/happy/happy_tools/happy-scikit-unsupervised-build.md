# Command-line

```
usage: happy-scikit-unsupervised-build [-h] [--repeat_num REPEAT_NUM]
                                       data_folder clusterer_name
                                       clusterer_params target_value
                                       happy_splitter_file output_folder

Evaluate clustering on hyperspectral data using specified clusterer and pixel
selector.

positional arguments:
  data_folder           Directory containing the hyperspectral data
  clusterer_name        Clusterer name (e.g., kmeans, agglomerative, spectral,
                        dbscan, meanshift)
  clusterer_params      JSON string containing clusterer parameters
  target_value          Target value column name
  happy_splitter_file   Happy Splitter file
  output_folder         Output JSON file to store the predictions

optional arguments:
  -h, --help            show this help message and exit
  --repeat_num REPEAT_NUM
                        Repeat number (default: 1) (default: 0)
```
