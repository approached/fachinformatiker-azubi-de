---
title: Image_colorspace
---

# Image_colorspace

## Get Colorspace

On Mac OS X

`sips -g space file.jpg`

On Linux:

`identify -format '%[colorspace]' file.jpg`
`or`
`identify -verbose file.jpg | grep Colorspace`

## Script

    #!/bin/bash

    echo "Checking jpg files..."
    expected="sRGB"

    for f in *.jpg;
    do
            colorspace=`identify -verbose $f | grep Colorspace | cut -d" " -f4`

    #echo $colorspace;

            if [ $colorspace != $expected ]
            then
                    echo "Bad file found: $f - $colorspace";
            fi
    done;

    echo "end"

## Note

-   <https://www.phpimagick.com/Imagick/transformImageColorspace>

`find . -iname "*.jpg" -exec jpeginfo -c {} \; | grep -E "Unsupported color conversion request"`
`find . -iname "*.jpg" -exec file {} \; | grep -e "CMYK" | cut -d" " -f1`
