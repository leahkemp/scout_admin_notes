# Get database logs

Find the file path to where the log files are written to with:

```bash
cat /etc/mongod.conf
```

or 

```bash
cat /yourMongoDBpath/mongod.conf
```

My output:

```bash
# mongod.conf

# for documentation of all options, see:
#   http://docs.mongodb.org/manual/reference/configuration-options/

# Where and how to store data.
storage:
  dbPath: /var/lib/mongodb
  journal:
    enabled: true
#  engine:
#  mmapv1:
#  wiredTiger:

# where to write logging data.
systemLog:
  destination: file
  logAppend: true
  path: /var/log/mongodb/mongod.log

# network interfaces
net:
  port: 27017
  bindIp: 127.0.0.1


# how the process runs
processManagement:
  timeZoneInfo: /usr/share/zoneinfo

#security:

#operationProfiling:

#replication:

#sharding:

## Enterprise-Only Options:

#auditLog:

#snmp:
```

This tells me the logs are written to `/var/log/mongodb/mongod.log`

Have a look at this log file

```bash
cat /var/log/mongodb/mongod.log
```
