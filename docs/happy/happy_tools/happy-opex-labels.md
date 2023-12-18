# Command-line

```
usage: happy-opex-labels [-h] -i INPUT [-r]
                         [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]
                         {list-labels,update-labels} ...

Performs actions on OPEX JSON files that it locates.

positional arguments:
  {list-labels,update-labels}
                        sub-command help
    list-labels         Lists the labels in the located files
    update-labels       Updates the labels using the specified label mapping

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        The dir with the OPEX JSON files (default: None)
  -r, --recursive       Whether to search the directory recursively (default:
                        False)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
