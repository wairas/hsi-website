# Command-line

```
usage: happy-opex2happy [-h] -i DIR [DIR ...] [-r] [-o DIR] -f
                        {flat,dir-tree,dir-tree-with-data} -l LABELS
                        [--black_ref_locator LOCATOR]
                        [--black_ref_method METHOD]
                        [--white_ref_locator LOCATOR]
                        [--white_ref_method METHOD] [-I] [-n] [-v]

Turns annotations (PNG and OPEX JSON) into Happy ENVI format.

optional arguments:
  -h, --help            show this help message and exit
  -i DIR [DIR ...], --input_dir DIR [DIR ...]
                        Path to the PNG/OPEX files (default: None)
  -r, --recursive       whether to look for OPEX files recursively (default:
                        False)
  -o DIR, --output_dir DIR
                        The directory to store the fake RGB PNG images instead
                        of alongside the HSI images. (default: None)
  -f {flat,dir-tree,dir-tree-with-data}, --output_format {flat,dir-tree,dir-tree-with-data}
                        Defines how to store the data in the output directory.
                        (default: flat)
  -l LABELS, --labels LABELS
                        The comma-separated list of object labels to export
                        ('Background' is automatically added). (default: None)
  --black_ref_locator LOCATOR
                        the reference locator scheme to use for locating black
                        references, eg rl-manual; requires: dir-tree-with-data
                        (default: None)
  --black_ref_method METHOD
                        the black reference method to use for applying black
                        references, eg br-same-size; requires: dir-tree-with-
                        data (default: None)
  --white_ref_locator LOCATOR
                        the reference locator scheme to use for locating
                        whites references, eg rl-manual; requires: dir-tree-
                        with-data (default: None)
  --white_ref_method METHOD
                        the white reference method to use for applying white
                        references, eg wr-same-size; requires: dir-tree-with-
                        data (default: None)
  -I, --include_input   whether to copy the PNG/JSON file across to the output
                        dir (default: False)
  -n, --dry_run         whether to omit generating any data or creating
                        directories (default: False)
  -v, --verbose         whether to be more verbose with the output (default:
                        False)
```
