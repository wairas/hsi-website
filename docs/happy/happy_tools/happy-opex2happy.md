# Command-line

```
usage: happy-opex2happy [-h] -i DIR [DIR ...] [-o DIR] -f {flat,dir-tree} -l
                        LABELS [-I] [-n] [-v]

Turns annotations (PNG and OPEX JSON) into Happy ENVI format.

optional arguments:
  -h, --help            show this help message and exit
  -i DIR [DIR ...], --input_dir DIR [DIR ...]
                        Path to the PNG/OPEX files (default: None)
  -o DIR, --output_dir DIR
                        The directory to store the fake RGB PNG images instead
                        of alongside the HSI images. (default: None)
  -f {flat,dir-tree}, --output_format {flat,dir-tree}
                        Defines how to store the data in the output directory.
                        (default: flat)
  -l LABELS, --labels LABELS
                        The comma-separated list of object labels to export
                        ('Background' is automatically added). (default: None)
  -I, --include_input   whether to copy the PNG/JSON file across to the output
                        dir (default: False)
  -n, --dry_run         whether to omit saving the PNG images (default: False)
  -v, --verbose         whether to be more verbose with the output (default:
                        False)
```
