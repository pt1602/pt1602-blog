---
title: "MySQL ANY command denied to user"
date: 2022-06-08T11:19:06+02:00
type: post
---

# MySQL ANY command denied to user

## Error
```shell
ERROR 1142 (42000) at line 11215: ANY command denied to user 'db-user-exported'@'%' for table 'dummy'
```

## Solution

### Create a copy
```shell
cp dev-dump.sql dev-dump-copy.sql
```

### Search and replace old user

__Old user:__ db-user-exported | __New user:__ db-user-target

__Old DB:__ db-exported | __New DB__ db-target

```shell
sed -i 's/db-user-target/db-user-exported/g' dev-dump-copy.sql
sed -i 's/db-target/db-exported/g' dev-dump-copy.sql
```

### Reimport
```shell
mysql -u db-user-exported -p db-exported < dev-dump-copy.sql
```

### mysqldump only definer
```shell
mysqldump --no-data --no-create-info --no-create-db --routines --triggers db-target > db-target-nodata.sql
```

### Search and Replace in definer
```shell
sed -i 's/db-user-target/db-user-exported/g' db-target-nodata.sql
sed -i 's/db-target/db-exported/g' db-target-nodata.sql
```

### Import only definer
```shell
mysql -u db-user-exported -p db-exported < db-target-nodata.sql
```

