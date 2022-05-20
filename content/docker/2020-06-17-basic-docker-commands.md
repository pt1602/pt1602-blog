---
title: Basic docker commands
author: pt1602
type: post
date: 2020-06-17T06:08:08+00:00
url: /basic-docker-commands/
categories:
  - basic
  - docker
tags:
  - basic
  - command
  - containers
  - docker
  - docker containers
  - docker-compose
  - start container
  - stop containers

---
Start a container:

> docker-compose up

Stop a container:

> docker-compose down

Kill all running containers:

> docker kill $(docker ps -q)