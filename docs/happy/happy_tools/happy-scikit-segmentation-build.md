# Command-line

```
usage: happy-scikit-segmentation-build [-h] -d HAPPY_DATA_BASE_DIR
                                       [-P PREPROCESSORS] [-S PIXEL_SELECTORS]
                                       [-m REGRESSION_METHOD] [-n NUM_CLASSES]
                                       [-p REGRESSION_PARAMS] -t TARGET_VALUE
                                       -s HAPPY_SPLITTER_FILE -o OUTPUT_FOLDER
                                       [-r REPEAT_NUM]
                                       [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Evaluate segmentation model on Happy Data using specified splits and pixel
selector.

optional arguments:
  -h, --help            show this help message and exit
  -d HAPPY_DATA_BASE_DIR, --happy_data_base_dir HAPPY_DATA_BASE_DIR
                        Directory containing the Happy Data files (default:
                        None)
  -P PREPROCESSORS, --preprocessors PREPROCESSORS
                        The preprocessors to apply to the data (default: )
  -S PIXEL_SELECTORS, --pixel_selectors PIXEL_SELECTORS
                        The pixel selectors to use. (default: simple-ps -n
                        32767)
  -m REGRESSION_METHOD, --regression_method REGRESSION_METHOD
                        Regression method name (e.g., randomforestclassifier,g
                        radientboostingclassifier,adaboostclassifier,kneighbor
                        sclassifier,decisiontreeclassifier,gaussiannb,logistic
                        regression,mlpclassifier,svm,random_forest,knn,decisio
                        n_tree,gradient_boosting,naive_bayes,logistic_regressi
                        on,neural_network,adaboost,extra_trees or full class
                        name) (default: svm)
  -n NUM_CLASSES, --num_classes NUM_CLASSES
                        The number of classes, used for generating the mapping
                        (default: 4)
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
