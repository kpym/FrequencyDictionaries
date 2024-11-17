# [FrequencyDictionaries](https://github.com/kpym/FrequencyDictionaries)

This repository contains frequency dictionaries in the form of text files, with one word per line.

The repository is organized into two folders:
- `freq_dicts_dirty`: Contains dictionaries with words that may not appear in a "standard" dictionary.
- `freq_dicts_clean`: Contains dictionaries that have been cleaned and supplemented to include only words found in a "standard" dictionary.

## `freq_dicts_dirty`

The files in this folder were derived from the [LuminosoInsight/wordfreq](https://github.com/LuminosoInsight/wordfreq) project. These dictionaries were converted into `.txt` files with one word per line, ordered by frequency (most frequent words come first). Only words longer than two characters were retained.

The conversion process involved:
1. Using the [jakm/msgpack-cli](https://github.com/jakm/msgpack-cli) tool to convert `.msgpack` files to `.json` format.
2. Transforming the `.json` files into `.txt` files with one word per line using `sed` and `grep`.

## `freq_dicts_clean`

The files in this folder were created by cleaning the dictionaries in the `freq_dicts_dirty` folder. This process involved removing words not found in the corresponding dictionaries from [titoBouzout/Dictionaries](https://github.com/titoBouzout/Dictionaries).

### File Naming Conventions
- Files named `short_xx.txt` retain their original names.
- Files originally named `long_xx.txt` have been renamed to `medium_xx.txt`.
- New `long_xx.txt` files are created from `medium_xx.txt` (or `short_xx.txt` when applicable). These are supplemented by appending, in alphabetical order, all words present in the "standard" dictionary but absent from the "frequency" dictionary.

## Licensing

This repository is licensed under the Apache License, Version 2.0. See the [LICENSE](LICENSE) file for details.

### Attribution and Data Licensing

This repository is based on two primary sources:

1. The [`rspeer/wordfreq`](https://github.com/rspeer/wordfreq) project by Robyn Speer.
2. Dictionaries from the [`titoBouzout/Dictionaries`](https://github.com/titoBouzout/Dictionaries) repository, originally derived from the OpenOffice dictionary list.

#### Wordfreq
- Robyn Speer must be credited as specified in [NOTICE.md](NOTICE.md).
- For a detailed list of data sources and their licenses, see the original `//wordfreq` [`NOTICE.md`](https://github.com/rspeer/wordfreq/blob/master/NOTICE.md).
- Data from `wordfreq/wordfreq` is redistributed under terms compatible with their original licenses, including the Creative Commons Attribution-ShareAlike 4.0 license.

#### Dictionaries
- The dictionaries included in this repository are derived from the OpenOffice dictionary list, as referenced in [`titoBouzout/Dictionaries`](https://github.com/titoBouzout/Dictionaries).
- While no formal license is provided in the source, credits to the original contributors are acknowledged in the respective `LANG.txt` files in the `titoBouzout/Dictionaries` repository.
- For more details about the dictionaries' origins and attribution requirements, see [NOTICE.md](NOTICE.md).

### Summary of Licensing

The combined content of this repository complies with the terms of the Apache License 2.0 and respects the attribution requirements of the original sources. See [NOTICE.md](NOTICE.md) for further details.
