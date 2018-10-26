# [FrequencyDictionaries](https://github.com/kpym/FrequencyDictionaries)

This repo contains frequency dictionaries that are text files with one word per line.

It is composed of two folders:
- `freq_dicts_dirty` : in this folder there the dictionaries contains words that are not in a "standard" dictionary.
- `freq_dicts_clean` : in this folder the dictionaries has been cleaned (and completed) to contain only words that are in a "standard" dictionary.

## freq_dicts_dirty

The files in this folder were obtained from [LuminosoInsight/wordfreq](https://github.com/LuminosoInsight/wordfreq) project.
The corresponding dictionaries were transformed to `.txt` files with one word per line (the more frequents come first) by keeping only the words longer than 2 characters.

The transformation was done using [jakm/msgpack-cli](https://github.com/jakm/msgpack-cli) tool to convert the `.msgpack` files to `.json` files, and then using `sed` and `grep` they are transformed to `.txt` files with one word per line.

## freq_dicts_clean

The files in this folder were obtained from the files in the `freq_dicts_dirty` folder by removing all words that are not in the corresponding dictionary of [titoBouzout/Dictionaries](https://github.com/titoBouzout/Dictionaries).

- every `short_xx.txt` file was named with the same name
- every `long_xx.txt` file was renamed to `medium_xx.txt`
- the files `long_xx.txt` are obtained from `medium_xx.txt` (or `short_xx.txt`) by completing them (at the end in alphabetical order) by all words that are in the "standard" dictionary but not present in the "frequency" dictionary.

