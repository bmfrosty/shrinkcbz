# shrinkcbz
quick and dirty tool to shrink cbr and cbz files which have oversize images.

I built this because some humble bundles come with 8-16k cbz/cbr files that break many android viewers.  It converts to 4k (2160 pix high)

It also converts them to webp now.

Please use with caution. It does not deal with edge cases well.  It may vomit, and depending on the source images, may take a long time to run.

# Requirements
* bash
* Imagemagick (convert) installed.
* rar
* unrar
* zip
* unzip

# Drawbacks
* Does not deal with cb7 files
* Does not deal with cba files
* Does not deal with cbt files
* Full of edge cases.

# How to use
* install Imagemagick
* Put the shrinkcbz script into your path

# Examples

## Convert a single file
```
shrinkcbz filename.cbz
```
## Convert every cbz file in a directory
```
for i in *.cbz ; do shrinkcbz $i ; done
```

## Notes for extremely large image files
I discovered this with the 2gb CBZ files that came in recent Manga HumbleBundle.

Specifically Parasyte Vol 1 & 2

You may need to update /etc/ImageMagick-6/policy.xml

Just comment out all the resource limits.  Example:

Change

` <policy domain="resource" name="memory" value="2048MiB"/>`

To

`  <!-- <policy domain="resource" name="memory" value="2048MiB"/>  -->`

Do this with all resource policies, and it should run again.

Beware that this will allow an extrememly large image to OOM your system.
