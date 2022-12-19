---
title: "ImageMagick batch resize"
date: 2022-12-19T05:19:19+02:00
type: post
---

## Requirement

* [ImageMagick](http://www.imagemagick.org/script/index.php)

### Installation

#### Debian/Ubuntu

```shell
sudo apt-get install imagemagick
```

#### MacOS/Brew

```shell
brew install ghostscript
brew install imagemagick
```

## Solution

Execute this in this directory with the images you want to resize. Do not forget to create a `small-jpgs` directory
before.

```shell
mogrify -path ../small-jpgs -resize 30% *
```

It is also possible to reduce the quality by adding `-quality 90` for example.

```shell
mogrify -path ../small-jpgs -quality 90 -resize 30% *
```

And if you want, you can even change the image format with `-format jpg`.

```shell
mogrify -path ../small-jpgs -quality 90 -format jpg -resize 30% *
```