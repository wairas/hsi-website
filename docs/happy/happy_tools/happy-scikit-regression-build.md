# Command-line

```
usage: happy-scikit-regression-build [-h] -d HAPPY_DATA_BASE_DIR
                                     [-P PREPROCESSORS] [-S PIXEL_SELECTORS]
                                     [-m REGRESSION_METHOD]
                                     [-p REGRESSION_PARAMS] -t TARGET_VALUE -s
                                     HAPPY_SPLITTER_FILE -o OUTPUT_FOLDER
                                     [-r REPEAT_NUM]
                                     [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Evaluate regression model on Happy Data using specified splits and pixel
selector.

optional arguments:
  -h, --help            show this help message and exit
  -d HAPPY_DATA_BASE_DIR, --happy_data_base_dir HAPPY_DATA_BASE_DIR
                        Directory containing the Happy Data files (default:
                        None)
  -P PREPROCESSORS, --preprocessors PREPROCESSORS
                        The preprocessors to apply to the data. Either
                        preprocessor command-line(s) or file with one
                        preprocessor command-line per line. (default:
                        wavelength-subset -f 60 -t 189 sni snv derivative -w
                        15 pad -W 128 -H 128 -v 0)
  -S PIXEL_SELECTORS, --pixel_selectors PIXEL_SELECTORS
                        The pixel selectors to use. Either pixel selector
                        command-line(s) or file with one pixel selector
                        command-line per line. (default: ps-simple -n 64)
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
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
