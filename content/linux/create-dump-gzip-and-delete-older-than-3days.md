---
title: "Gitlab create dump, gzip and delete everything older than 3 days"
date: 2022-06-08T11:19:06+02:00
type: post
---

```shell
mysqldump -h localhost -u $MYSQL_USER -p"$MYSQL_PASSWORD" --no-tablespaces $MYSQL_TABLE | gzip > dump-$CI_COMMIT_TAG.gz && ls -t | sed -e '1,3d' | xargs -d '\n' rm
```
