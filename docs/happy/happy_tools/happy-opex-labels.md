# Command-line

```
usage: happy-opex-labels [-h] -i INPUT [INPUT ...] [-r] [-a {list-labels}]
                         [-o OUTPUT_FILE]
                         [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Performs actions on OPEX JSON files that it locates.

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT [INPUT ...], --input INPUT [INPUT ...]
                        The dir(s) with the OPEX JSON files (default: None)
  -r, --recursive       Whether to search the directory recursively (default:
                        False)
  -a {list-labels}, --action {list-labels}
                        The action to perform (default: list-labels)
  -o OUTPUT_FILE, --output_file OUTPUT_FILE
                        Path to the output file; outputs to stdout if omitted
                        (default: None)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
