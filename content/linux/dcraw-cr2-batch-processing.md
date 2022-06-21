---
title: dcraw cr2 batch processing
author: pt1602
type: post
---
I searched two times for this, so I am going to save this here. With the following command you can convert all raws(cr2) in your current directory to jpg.

```for filename in *.CR2; do dcraw -c -w "$filename" | cjpeg -quality 90 > "$filename.jpg"; echo $filename done; done;```