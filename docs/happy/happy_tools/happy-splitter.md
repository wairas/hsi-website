# Command-line

```
usage: happy-splitter [-h] [--num_repeats NUM_REPEATS] [--num_folds NUM_FOLDS]
                      [--train_percent TRAIN_PERCENT]
                      [--validation_percent VALIDATION_PERCENT]
                      [--use_regions] [--holdout_percent HOLDOUT_PERCENT]
                      [--output_file OUTPUT_FILE]
                      happy_base_folder

Generate train/validation/test splits for Happy data.

positional arguments:
  happy_base_folder     Path to the Happy base folder

optional arguments:
  -h, --help            show this help message and exit
  --num_repeats NUM_REPEATS
                        Number of repeats (default: 1)
  --num_folds NUM_FOLDS
                        Number of folds (default: 1)
  --train_percent TRAIN_PERCENT
                        Percentage of data in the training set (default: 70.0)
  --validation_percent VALIDATION_PERCENT
                        Percentage of data in the validation set (default:
                        10.0)
  --use_regions         Use regions in generating splits (default: False)
  --holdout_percent HOLDOUT_PERCENT
                        Percentage of data to hold out as a holdout set
                        (default: None)
  --output_file OUTPUT_FILE
                        Path to the output split file (default:
                        output_split.json)
```
