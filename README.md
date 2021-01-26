# compress-pptx

Compress a PPTX file, converting all PNG/TIFF images to lossy JPEGs.

## What it does

When copy-pasting images to PowerPoint presentations, these sometimes get inserted as lossless versions, blowing up the size of the presentation.

This script takes all PNG or TIFF images part of the presentation which are larger than a given threshold (1 MiB by default), converts them to a lossy JPEG variant, and creates a new PPTX file.

:warning: This will not work for PNG images containing transparency!

## Requirements

This script runs under *nix systems and presumably also WSL.

- Bash
- Perl
- ImageMagick's `convert`
- `zip` and `unzip`

Under Ubuntu, get those via:

```
apt install zip unzip imagemagick
```

## Installation

Simply download the `compress_pptx.sh` file and execute it:

```
wget https://raw.githubusercontent.com/slhck/compress-pptx/main/compress_pptx.sh
chmod +x compress_pptx.sh
./compress_pptx.sh
```

## Usage

Call the script and point it to a PPTX file. It'll compress the images and output another compressed file next to it.

For more options, see the `-h` output:

```
./compress_pptx.sh [-s SIZE] [-q QUALITY] [-o OUTPUT] <input>

  -s SIZE     Minimum size in MiB for images to be compressed (default: 1)
  -q QUALITY  JPEG quality from 0-100 (default: 85)
  -o OUTPUT   Output file (default: input file with '-compressed.pptx' suffix)
```

## Version history

- v0.1: Initial release

## License

MIT License

Copyright (c) 2021 Werner Robitza

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
