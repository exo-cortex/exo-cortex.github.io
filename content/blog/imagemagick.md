---
title: "easy image manipulation using imagemagick"
date: 2021-06-02T16:20:26+02:00
draft: false
---

I often use [**Imagemagick**](https://en.wikipedia.org/wiki/ImageMagick) for simple image-manipulation from the commandline. To use the program run the command "convert".

The following is a collection of useful commands for simple image manipulation like resizing, cropping or conversion from one format to another. This collection exists, because I realized that I had to re-google some commands everytime I was using them.

## conversion between formats
```bash
$ convert input_image.png -quality 90 output_image.jpg
# or set output format through "-format"-option
$ convert input_image.png -quality 90 -format jpg output_image
```

## resize an image
```bash
# resize with relative size argument.
$ convert input_image.png -resize 50% smaller_output_image.png
# resize with absolute size argument.
$ convert input_image.png -resize 300 output_image.png
# resize with absolute size argument, disregard aspect ration.
$ convert input_image.png -resize 300x500 stretched_output_image.png
```

## cropping images

```bash
# cropping an image to 100x50 with an offset 25 pixels from the left and 10 pixels from the top
$ convert -crop 100x50+25+10 input_image.png output_image.png
```

## reduzing the number of colors
```bash
# reducing the number of colors to 10
$ convert -colors 10 input_image.png output_image.png
```
