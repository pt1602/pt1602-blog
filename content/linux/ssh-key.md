---
title: "SSH Key"
date: 2022-06-08T11:19:06+02:00
type: post
---

Thanks to the [talk](https://www.youtube.com/watch?v=qvdlLTyUJ5I) of [Martin Leyrer](https://martin.leyrer.priv.at/) my ssh-keys now get generated like this:

`ssh-keygen -t ed25519 -a 420 -f ~/.ssh/id_ed25519 -C "foo@ba.de"`
