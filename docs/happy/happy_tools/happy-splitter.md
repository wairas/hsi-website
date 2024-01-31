# Command-line

```
usage: happy-splitter [-h] -d HAPPY_BASE_FOLDER [-r NUM_REPEATS]
                      [-f NUM_FOLDS] [-t TRAIN_PERCENT]
                      [-v VALIDATION_PERCENT] [-R] [-H HOLDOUT_PERCENT] -o
                      OUTPUT_FILE [-S SEED]

Generate train/validation/test splits for Happy data.

optional arguments:
  -h, --help            show this help message and exit
  -d HAPPY_BASE_FOLDER, --happy_base_folder HAPPY_BASE_FOLDER
                        Path to the Happy base folder (default: None)
  -r NUM_REPEATS, --num_repeats NUM_REPEATS
                        Number of repeats (default: 1)
  -f NUM_FOLDS, --num_folds NUM_FOLDS
                        Number of folds (default: 1)
  -t TRAIN_PERCENT, --train_percent TRAIN_PERCENT
                        Percentage of data in the training set (default: 70.0)
  -v VALIDATION_PERCENT, --validation_percent VALIDATION_PERCENT
                        Percentage of data in the validation set (default:
                        10.0)
  -R, --use_regions     Use regions in generating splits (default: False)
  -H HOLDOUT_PERCENT, --holdout_percent HOLDOUT_PERCENT
                        Percentage of data to hold out as a holdout set
                        (default: None)
  -o OUTPUT_FILE, --output_file OUTPUT_FILE
                        Path to the output split file (default:
                        output_split.json)
  -S SEED, --seed SEED  The seed to use for reproducible results (default:
                        None)
```
