# Useful commands for admins working with scout

Created: 2020/10/12 15:35:50
Last modified: 2021/07/08 12:44:28

## Table of contents

- [Useful commands for admins working with scout](#useful-commands-for-admins-working-with-scout)
  - [Table of contents](#table-of-contents)
  - [View the institute and users](#view-the-institute-and-users)
  - [Deleting 'old' cases](#deleting-old-cases)
  - [View the underlying mongod databases and delete them if needed](#view-the-underlying-mongod-databases-and-delete-them-if-needed)
  - [Back up database](#back-up-database)
  - [Uninstall mongodb community edition](#uninstall-mongodb-community-edition)

## View the institute and users

```bash
scout -db dhb-database view institutes
scout -db dhb-database view users
```

## Deleting 'old' cases

```bash
scout -db dhb-database delete case -i DHB -c CH_13BL2450_S1
```

## View the underlying mongod databases and delete them if needed

```bash
mongo # Open a mongo shell
show dbs
use scout-demo
db.dropDatabase()
quit() # Exit mongo shell
```

## Back up database

The scout database can be backed up by backing up the underlying mongo database (see [these docs](https://docs.mongodb.com/manual/core/backups/))

```bash
mongodump
```

## Uninstall mongodb community edition

(see [these docs](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/#uninstall-mongodb-community-edition))

```bash
sudo service mongod stop
sudo apt-get purge mongodb-org*
sudo rm -r /var/log/mongodb
sudo rm -r /var/lib/mongodb
```
