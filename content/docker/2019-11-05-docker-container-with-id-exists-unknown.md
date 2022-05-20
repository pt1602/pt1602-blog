---
title: docker container with id exists unknown
author: pt1602
type: post
date: 2019-11-05T07:19:40+00:00
url: /docker-container-with-id-exists-unknown/
categories:
  - docker
  - everything
  - WSL 2
tags:
  - container
  - docker
  - exists
  - linux
  - linux in windows
  - wsl
  - wsl2

---
Remove all existing docker containers with the command:

> docker container rm -v

Get a list of current containers

> docker ps -a

remove specific containers

> docker container rm <container-id>