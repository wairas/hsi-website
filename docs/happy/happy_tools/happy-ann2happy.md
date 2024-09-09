# Command-line

```
usage: happy-ann2happy [-h] -i DIR [DIR ...] [--regexp REGEXP]
                       [-c {pixels,polygons,pixels_then_polygons,polygons_then_pixels}]
                       [-r] [-o DIR] -f {flat,dir-tree,dir-tree-with-data} -l
                       LABELS [-N] [-u UNLABELLED]
                       [--black_ref_locator LOCATOR]
                       [--black_ref_method METHOD]
                       [--white_ref_locator LOCATOR]
                       [--white_ref_method METHOD]
                       [--white_ref_annotations FILE]
                       [--black_ref_locator_for_white_ref LOCATOR]
                       [--black_ref_method_for_white_ref METHOD]
                       [--pattern_mask PATTERN] [--pattern_labels PATTERN]
                       [--pattern_png PATTERN] [--pattern_opex PATTERN]
                       [--pattern_envi PATTERN] [-I] [-n] [--resume_from DIR]
                       [-V {DEBUG,INFO,WARNING,ERROR,CRITICAL}]

Turns annotations (PNG, OPEX JSON, ENVI pixel annotations) into Happy ENVI
format.

optional arguments:
  -h, --help            show this help message and exit
  -i DIR [DIR ...], --input_dir DIR [DIR ...]
                        Path to the PNG/OPEX/ENVI files (default: None)
  --regexp REGEXP       The regexp for matching the ENVI base files (name
                        only), e.g., for selecting a subset. (default: None)
  -c {pixels,polygons,pixels_then_polygons,polygons_then_pixels}, --conversion {pixels,polygons,pixels_then_polygons,polygons_then_pixels}
                        What annotations and in what order to apply
                        (subsequent overlays can overwrite annotations).
                        (default: pixels_then_polygons)
  -r, --recursive       whether to look for OPEX/ENVI files recursively
                        (default: False)
  -o DIR, --output_dir DIR
                        The directory to store the fake RGB PNG images instead
                        of alongside the HSI images. (default: None)
  -f {flat,dir-tree,dir-tree-with-data}, --output_format {flat,dir-tree,dir-tree-with-data}
                        Defines how to store the data in the output directory.
                        (default: dir-tree-with-data)
  -l LABELS, --labels LABELS
                        The comma-separated list of object labels to export
                        ('Background' is automatically added). (default: None)
  -N, --no_implicit_background
                        whether to require explicit annotations for the
                        background rather than assuming all un-annotated
                        pixels are background (default: False)
  -u UNLABELLED, --unlabelled UNLABELLED
                        The value to use for pixels that do not have an
                        explicit annotation (label values start after this
                        value) (default: 0)
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
  --pattern_mask PATTERN
                        the pattern to use for saving the mask ENVI file,
                        available placeholders: {SAMPLEID} (default: mask.hdr)
  --pattern_labels PATTERN
                        the pattern to use for saving the label map for the
                        mask ENVI file, available placeholders: {SAMPLEID}
                        (default: mask.json)
  --pattern_png PATTERN
                        the pattern to use for saving the mask PNG file,
                        available placeholders: {SAMPLEID} (default:
                        {SAMPLEID}.png)
  --pattern_opex PATTERN
                        the pattern to use for saving the OPEX JSON annotation
                        file, available placeholders: {SAMPLEID} (default:
                        {SAMPLEID}.json)
  --pattern_envi PATTERN
                        the pattern to use for saving the ENVI mask annotation
                        file, available placeholders: {SAMPLEID} (default:
                        MASK_{SAMPLEID}.hdr)
  -I, --include_input   whether to copy the PNG/JSON file across to the output
                        dir (default: False)
  -n, --dry_run         whether to omit generating any data or creating
                        directories (default: False)
  --resume_from DIR     The directory to restart the processing with (all
                        determined dirs preceding this one get skipped)
                        (default: None)
  -V {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --logging_level {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                        The logging level to use. (default: WARN)
```
