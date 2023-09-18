# Command-line

```
usage: happy-scikit-regression-build [-h] [--repeat_num REPEAT_NUM]
                                     happy_data_base_dir regression_method
                                     regression_params target_value
                                     happy_splitter_file output_folder

Evaluate regression model on Happy Data using specified splits and pixel
selector.

positional arguments:
  happy_data_base_dir   Directory containing the Happy Data files
  regression_method     Regression method name
  regression_params     JSON string containing regression parameters
  target_value          Target value column name
  happy_splitter_file   Happy Splitter file
  output_folder         Output JSON file to store the predictions

optional arguments:
  -h, --help            show this help message and exit
  --repeat_num REPEAT_NUM
                        Repeat number (default: 1) (default: 0)
```
