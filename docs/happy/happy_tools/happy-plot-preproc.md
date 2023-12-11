# Command-line

```
usage: happy-plot-preproc [-h] -i INPUT_DIR [-f FROM_INDEX] [-t TO_INDEX]
                          [-P PREPROCESSORS] [-S PIXEL_SELECTORS]
                          [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Plot set of pixels with various pre-processing setups.

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT_DIR, --input_dir INPUT_DIR
                        Folder containing HAPPy data files (default: None)
  -f FROM_INDEX, --from_index FROM_INDEX
                        The first wavelength index to include (0-based)
                        (default: 60)
  -t TO_INDEX, --to_index TO_INDEX
                        The last wavelength index to include (0-based)
                        (default: 189)
  -P PREPROCESSORS, --preprocessors PREPROCESSORS
                        The preprocessors to apply to the data separately; use
                        "multi-pp" if you need to combine multiple steps.
                        Either preprocessor command-line(s) or file with one
                        preprocessor command-line per line. (default: pass-
                        through multi-pp -p 'derivative -w 15 -d 0 snv'
                        derivative -w 15 -d 0 sni)
  -S PIXEL_SELECTORS, --pixel_selectors PIXEL_SELECTORS
                        The pixel selectors to use. Either pixel selector
                        command-line(s) or file with one pixel selector
                        command-line per line. (default: ps-simple -n 100 -b)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
