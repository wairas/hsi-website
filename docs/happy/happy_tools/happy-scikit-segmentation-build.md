# Command-line

```
usage: happy-scikit-segmentation-build [-h] -d HAPPY_DATA_BASE_DIR
                                       [-P PREPROCESSORS] [-S PIXEL_SELECTORS]
                                       [-m SEGMENTATION_METHOD]
                                       [-p SEGMENTATION_PARAMS] -t
                                       TARGET_VALUE -s HAPPY_SPLITTER_FILE -o
                                       OUTPUT_FOLDER [-r REPEAT_NUM]
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
                        The pixel selectors to use. (default: ps-simple -n
                        32767)
  -m SEGMENTATION_METHOD, --segmentation_method SEGMENTATION_METHOD
                        Segmentation method name (e.g., randomforestclassifier
                        ,gradientboostingclassifier,adaboostclassifier,kneighb
                        orsclassifier,decisiontreeclassifier,gaussiannb,logist
                        icregression,mlpclassifier,svm,random_forest,knn,decis
                        ion_tree,gradient_boosting,naive_bayes,logistic_regres
                        sion,neural_network,adaboost,extra_trees or full class
                        name) (default: svm)
  -p SEGMENTATION_PARAMS, --segmentation_params SEGMENTATION_PARAMS
                        JSON string containing segmentation parameters
                        (default: {})
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
