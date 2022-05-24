---
title: "Keep Three Newest Files"
date: 2022-05-24T10:41:03+02:00
draft: true
---


```
ls -t | sed -e '1,3d' | xargs -d '\n' rm
```

## What's going on here?


`ls -t` 
lists all files in the current directory in decreasing order of modification time. The most recently modified files are first, one file name per line.

`sed -e '1,3d'` deletes the first 3 lines, the 3 newest files.

`rm` collects each input line (without the terminating newline) and passes each line as an argument to `rm`

[Source](https://stackoverflow.com/questions/2960022/shell-script-to-count-files-then-remove-oldest-files)