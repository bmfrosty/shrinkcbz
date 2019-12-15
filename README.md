# shrinkcbz
quick and dirty tool to shrink cbz files which have oversize images.
I built this because some humblebundles come with 8k cbz/cbr files that break many android viewers.  It converts to 4k (2160 pix high)
Please use with caution. It does not deal with edge cases well.  It may vomit, and depending on the source images, may take a long time to run.

# Requirements
* bash
* Imagemagick (convert) installed.

# Drawbacks
* Does not deal with cb7 files
* Does not deal with cba files
* Does not deal with cbr files
* Does not deal with cbt files
* Full of edge cases.

# How to use
* install Imagemagick
* Put the two shell scripts (shrinkcbz and randomstring) into your path

# Examples

## Convert a single file
```
shrinkcbz filename.cbz
```
## Convert every cbz file in a directory
```
for i in *.cbz ; do shrinkcbz $i ; done
```
