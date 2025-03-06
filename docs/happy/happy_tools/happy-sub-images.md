# Command-line

```
usage: happy-sub-images [-h] -i DIR [DIR ...] [-e REGEXP] [-r]
                        [-o DIR [DIR ...]] [-w CMDLINE [CMDLINE ...]]
                        [-l LABELS] [--black_ref_locator LOCATOR]
                        [--black_ref_method METHOD]
                        [--white_ref_locator LOCATOR]
                        [--white_ref_method METHOD]
                        [--white_ref_annotations FILE]
                        [--black_ref_locator_for_white_ref LOCATOR]
                        [--black_ref_method_for_white_ref METHOD]
                        [--preprocessing PIPELINE] [-n] [-R DIR] [-I FILE]
                        [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Exports sub-images from ENVI files annotated with OPEX JSON files. Used for
extracting sub-samples. Multiple output/writer pairs can be specified to
output in multiple formats in one go.

optional arguments:
  -h, --help            show this help message and exit
  -i DIR [DIR ...], --input_dir DIR [DIR ...]
                        Path to the files to generate sub-images from
                        (default: None)
  -e REGEXP, --regexp REGEXP
                        The regexp for matching the ENVI base files (name
                        only), e.g., for selecting a subset. (default: None)
  -r, --recursive       whether to look for files recursively (default: False)
  -o DIR [DIR ...], --output_dir DIR [DIR ...]
                        The dir(s) to store the generated sub-images in.
                        (default: None)
  -w CMDLINE [CMDLINE ...], --writer CMDLINE [CMDLINE ...]
                        the writer(s) to use for saving the generated sub-
                        images (default: happy-writer)
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
  --white_ref_annotations FILE
                        the OPEX JSON file with the annotated white reference
                        if it cannot be determined automatically (default:
                        None)
  --black_ref_locator_for_white_ref LOCATOR
                        the reference locator scheme to use for locating black
                        references that get applied to the white reference, eg
                        rl-manual (default: None)
  --black_ref_method_for_white_ref METHOD
                        the black reference method to use for applying black
                        references to the white reference, eg br-same-size
                        (default: None)
  --preprocessing PIPELINE
                        the preprocessors to apply to the scan (default: None)
  -n, --dry_run         whether to omit generating any data or creating
                        directories (default: False)
  -R DIR, --resume_from DIR
                        The directory to restart the processing with (all
                        determined dirs preceding this one get skipped)
                        (default: None)
  -I FILE, --run_info FILE
                        The JSON file to store some run information in.
                        (default: None)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```

# Examples

Below are some examples for converting raw scans into various output formats.

## CSV

The command below instructs the `csv-writer` to combine all regions for
a sample into a single file by not having the `{REGION}` (or `{REPEAT}`)
placeholder in the output pattern. `{BASEDIR}` is the output directory 
supplied to `happy-sub-images`. Black reference files are automatically
determined using the `--black_ref_locator` option and the `{PATH}/DARKREF_{NAME}.hdr`
pattern. The `br-col-avg` black reference method computes the average
per band and column (requires scan and reference to have same number of columns).
Only annotations that match the expression `[0-9]+` are being exported:

```bash
happy-sub-images \
  -V INFO \
  -i "/some/where/raw/" \
  -r \
  --black_ref_locator "rl-file-pattern -p \"{PATH}/DARKREF_{NAME}.hdr\"" \
  --black_ref_method br-col-avg \
  -l "[0-9]+" \
  -o /some/where/csv/ \
  --writer "csv-writer -o {BASEDIR}/{SAMPLEID}.csv" 
```

## ENVI

The command below exports the regions of all samples separately as plain ENVI files.
Just like with the CSV example above, black references are automatically
determined based on their file name:

```bash
happy-sub-images \
  -V INFO \
  -i "/some/where/raw/" \
  -r \
  --black_ref_locator "rl-file-pattern -p \"{PATH}/DARKREF_{NAME}.hdr\"" \
  --black_ref_method br-col-avg \
  -l "[0-9]+" \
  -o /some/where/envi/ \
  --writer envi-writer 
```

## HappyData

By converting the scans into the HappyData format, you can view them later
in the [Data Viewer](../happy_tools_tkinter/happy-data-viewer.md) and then also build models.
The command below only processes samples that match the regular expression
`"A_1_1.*"`. The white reference for this subset of scans is stored in a 
separate scan folder (`--white_ref_locator "rl-fixed ...`) and has its
own OPEX JSON file with a single `whiteref` annotation 
(`--white_ref_annotations "/some...`) which gets applied after the black
reference has been applied. Since the white ref is a separate scan,
a black reference can be applied as well using the options 
`--black_ref_locator_for_white_ref` and `--black_ref_method_for_white_ref`:

```bash
happy-sub-images \
  -V INFO \
  -i "/some/where/raw/" \
  --regexp "A_1_1.*" \
  -r \
  --black_ref_locator "rl-file-pattern -p \"{PATH}/DARKREF_{NAME}.hdr\"" \
  --black_ref_method br-col-avg \
  --white_ref_locator "rl-fixed -f \"/some/where/raw/A_White_Ref_2024-08-19_22-11-04/capture/A_White_Ref_2024-08-19_22-11-04.hdr\"" \
  --white_ref_method wr-annotation-avg \
  --white_ref_annotations "/some/where/raw/A_White_Ref_2024-08-19_22-11-04/capture/A_White_Ref_2024-08-19_22-11-04.json" \
  --black_ref_locator_for_white_ref "rl-fixed -f \"/some/where/raw/A_White_Ref_2024-08-19_22-11-04/capture/DARKREF_A_White_Ref_2024-08-19_22-11-04.hdr\"" \
  --black_ref_method_for_white_ref br-col-avg \
  -l "[0-9]+" \
  -o /some/where/happy/ \
  --writer happy-writer
```

## Matlab

The same command, but this time generating Matlab files using the `matlab-writer`:

```bash
happy-sub-images \
  -V INFO \
  -i "/some/where/raw/" \
  --regexp "A_1_1.*" \
  -r \
  --black_ref_locator "rl-file-pattern -p \"{PATH}/DARKREF_{NAME}.hdr\"" \
  --black_ref_method br-col-avg \
  --white_ref_locator "rl-fixed -f \"/some/where/raw/A_White_Ref_2024-08-19_22-11-04/capture/A_White_Ref_2024-08-19_22-11-04.hdr\"" \
  --white_ref_method wr-annotation-avg \
  --white_ref_annotations "/some/where/raw/A_White_Ref_2024-08-19_22-11-04/capture/A_White_Ref_2024-08-19_22-11-04.json" \
  --black_ref_locator_for_white_ref "rl-fixed -f \"/some/where/raw/A_White_Ref_2024-08-19_22-11-04/capture/DARKREF_A_White_Ref_2024-08-19_22-11-04.hdr\"" \
  --black_ref_method_for_white_ref br-col-avg \
  -l "[0-9]+" \
  -o /some/where/matlab/ \
  --writer matlab-writer
```

## PNG

Images can be generated with the `image-writer`, with the extension defined in 
the output pattern determining the image type.
The `--suppress_metadata` option of the `image-writer` suppresses the output of the
JSON companion files containing information about the region:

```bash
happy-sub-images \
  -V INFO \
  -i "/some/where/raw/" \
  -r \
  --black_ref_locator "rl-file-pattern -p \"{PATH}/DARKREF_{NAME}.hdr\"" \
  --black_ref_method br-col-avg \
  -l "[0-9]+" \
  -o /some/where/png/ \
  --writer "image-writer --suppress_metadata -R 95 -G 152 -B 111 -o {BASEDIR}/{SAMPLEID}.{REGION}.png" 
```

## Multiple output formats

By supplying multiple output/writer pairs, multiple output formats can be generated
with a single pass. The following command generates CSV, Matlab and PNG output:

```bash
happy-sub-images \
  -V INFO \
  -i "/some/where/raw/" \
  -r \
  --black_ref_locator "rl-file-pattern -p \"{PATH}/DARKREF_{NAME}.hdr\"" \
  --black_ref_method br-col-avg \
  -l "[0-9]+" \
  -o \
    /some/where/csv/ \
    /some/where/matlab/ \
    /some/where/png/ \
  --writer \
    "csv-writer -o {BASEDIR}/{SAMPLEID}.csv" \
    matlab-writer \
    "image-writer --suppress_metadata -R 95 -G 152 -B 111 -o {BASEDIR}/{SAMPLEID}.{REGION}.png"
```
