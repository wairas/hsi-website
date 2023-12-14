# Command-line

```
usage: happy-raw-check [-h] -i INPUT [INPUT ...] [-r] [-o OUTPUT]
                       [-f {text,csv,json}]
                       [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Performs sanity checks on raw capture folders.

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT [INPUT ...], --input INPUT [INPUT ...]
                        The dir(s) with the raw capture folders (default:
                        None)
  -r, --recursive       Whether to search the directory recursively (default:
                        False)
  -o OUTPUT, --output OUTPUT
                        The file to store the results in; uses stdout if
                        omitted (default: None)
  -f {text,csv,json}, --output_format {text,csv,json}
                        The format to use for the output (default: text)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
