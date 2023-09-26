# Command-line

```
usage: happy-scikit-regression-build [-h] -d HAPPY_DATA_BASE_DIR
                                     [-m REGRESSION_METHOD]
                                     [-p REGRESSION_PARAMS] -t TARGET_VALUE -s
                                     HAPPY_SPLITTER_FILE -o OUTPUT_FOLDER
                                     [-r REPEAT_NUM]

Evaluate regression model on Happy Data using specified splits and pixel
selector.

optional arguments:
  -h, --help            show this help message and exit
  -d HAPPY_DATA_BASE_DIR, --happy_data_base_dir HAPPY_DATA_BASE_DIR
                        Directory containing the Happy Data files (default:
                        None)
  -m REGRESSION_METHOD, --regression_method REGRESSION_METHOD
                        Regression method name (e.g., linearregression,ridge,l
                        ars,plsregression,plsneighbourregression,lasso,elastic
                        net,decisiontreeregressor,randomforestregressor,svr or
                        full class name) (default: linearregression)
  -p REGRESSION_PARAMS, --regression_params REGRESSION_PARAMS
                        JSON string containing regression parameters (default:
                        {})
  -t TARGET_VALUE, --target_value TARGET_VALUE
                        Target value column name (default: None)
  -s HAPPY_SPLITTER_FILE, --happy_splitter_file HAPPY_SPLITTER_FILE
                        Happy Splitter file (default: None)
  -o OUTPUT_FOLDER, --output_folder OUTPUT_FOLDER
                        Output JSON file to store the predictions (default:
                        None)
  -r REPEAT_NUM, --repeat_num REPEAT_NUM
                        Repeat number (default: 0) (default: 0)
```
