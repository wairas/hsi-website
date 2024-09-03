# Command-line

```
usage: happy-sub-images [-h] -i DIR [DIR ...] [--regexp REGEXP] [-r] [-o DIR]
                        [-l LABELS] [--black_ref_locator LOCATOR]
                        [--black_ref_method METHOD]
                        [--white_ref_locator LOCATOR]
                        [--white_ref_method METHOD] [--writer CMDLINE] [-n]
                        [--resume_from DIR]
                        [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Exports sub-images from ENVI files annotated with OPEX JSON files. Used for
extracting sub-samples.

optional arguments:
  -h, --help            show this help message and exit
  -i DIR [DIR ...], --input_dir DIR [DIR ...]
                        Path to the files to generate sub-images from
                        (default: None)
  --regexp REGEXP       The regexp for matching the ENVI base files (name
                        only), e.g., for selecting a subset. (default: None)
  -r, --recursive       whether to look for files recursively (default: False)
  -o DIR, --output_dir DIR
                        The directory to store the generated sub-images in.
                        (default: None)
  -l LABELS, --labels LABELS
                        The regexp for the labels to export. (default: None)
  --black_ref_locator LOCATOR
                        the reference locator scheme to use for locating black
                        references, eg rl-manual (default: None)
  --black_ref_method METHOD
                        the black reference method to use for applying black
                        references, eg br-same-size (default: None)
  --white_ref_locator LOCATOR
                        the reference locator scheme to use for locating
                        whites references, eg rl-manual (default: None)
  --white_ref_method METHOD
                        the white reference method to use for applying white
                        references, eg wr-same-size (default: None)
  --writer CMDLINE      the writer to use for saving the generated sub-images
                        (default: happy-writer)
  -n, --dry_run         whether to omit generating any data or creating
                        directories (default: False)
  --resume_from DIR     The directory to restart the processing with (all
                        determined dirs preceding this one get skipped)
                        (default: None)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
