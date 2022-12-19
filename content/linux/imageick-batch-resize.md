---
title: "Imageick batch resize"
date: 2022-12-19T05:19:19+02:00
type: post
---

Execute this in this directory with the images you want to resize. Do not forget to create a `small-jpgs` directory
before.

```shell
mogrify -path ../small-jpgs -resize 30% *
```