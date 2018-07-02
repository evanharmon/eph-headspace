# Couchbase Server Logging in AWS
```
[couchbase]
datetime_format = %Y-%m-%dT%H:%M:%S
file = /opt/couchbase/var/lib/couchbase/logs/couchdb.log
buffer_duration = 5000
log_stream_name = {instance_id}
initial_position = start_of_file
log_group_name = couchbase
```
