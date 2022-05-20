---
title: dcraw cr2 batch processing
author: pt1602
type: post
date: 2020-12-06T09:58:47+00:00
url: /dcraw-cr2-batch-processing/
categories:
  - bash
  - everything
  - linux
  - ubuntu
tags:
  - bash
  - batch
  - convert
  - cr2
  - dcraw
  - jpg
  - linux
  - photo
  - photography
  - processing
  - raw

---
I searched two times for this, so I am going to save this here. With the following command you can convert all raws(cr2) in your current directory to jpg.

> for filename in *.CR2; do dcraw -c -w &#8220;$filename&#8221; | cjpeg -quality 90 > &#8220;$filename.jpg&#8221;; echo $filename done; done;