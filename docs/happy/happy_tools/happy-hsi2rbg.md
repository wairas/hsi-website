# Command-line

```
usage: happy-hsi2rgb [-h] -i INPUT_DIR [INPUT_DIR ...] [-r] [-e EXTENSION]
                     [--black_ref_locator LOCATOR] [--black_ref_method METHOD]
                     [--white_ref_locator LOCATOR] [--white_ref_method METHOD]
                     [-a] [--red INT] [--green INT] [--blue INT]
                     [-o OUTPUT_DIR] [--width INT] [--height INT] [-n]
                     [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Fake RGB image generator for HSI files.

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT_DIR [INPUT_DIR ...], --input_dir INPUT_DIR [INPUT_DIR ...]
                        Path to the scan file (ENVI format) (default: None)
  -r, --recursive       whether to traverse the directories recursively
                        (default: False)
  -e EXTENSION, --extension EXTENSION
                        The file extension to look for (default: .hdr)
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
  -a, --autodetect_channels
                        whether to determine the channels from the meta-data
                        (overrides the manually specified channels) (default:
                        False)
  --red INT             the wave length to use for the red channel (0-based)
                        (default: 0)
  --green INT           the wave length to use for the green channel (0-based)
                        (default: 0)
  --blue INT            the wave length to use for the blue channel (0-based)
                        (default: 0)
  -o OUTPUT_DIR, --output_dir OUTPUT_DIR
                        The directory to store the fake RGB PNG images instead
                        of alongside the HSI images. (default: None)
  --width INT           the width to scale the images to (<= 0 uses image
                        dimension) (default: 0)
  --height INT          the height to scale the images to (<= 0 uses image
                        dimension) (default: 0)
  -n, --dry_run         whether to omit saving the PNG images (default: False)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
