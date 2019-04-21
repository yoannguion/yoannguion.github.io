---
layout: post
title: "Automatic check, repair, optimize mysql database"
---

# Automatic check, repair, optimize mysql database

To check, repair MySQL databases

```
mysqlcheck -u user -p --auto-repair --all-databases
```

Optimize MySQL databases

```
mysqlcheck -u user -p --optimize --all-databases
```

## Automatisation

We will use a cron task, so we create an executable file /etc/cron.daily/mysql-repair-optimize

```
#!/bin/bash
mysqlcheck -u user --auto-repair --all-databases
mysqlcheck -u user --optimize --all-databases

```

This cron is launch by root and we do not want to see root password in command line

We create a root file /root/.my.cnf

```
[client]
password=xxxxxxx
```

this /root/.my.cnf file contains in our case user mysql password  ;)

sources:  http://dev.mysql.com/doc/refman/5.0/en/password-security-user.html