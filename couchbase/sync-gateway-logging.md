# SYNC GATEWAY LOGGING

## Log Path
Changing location depends where you put it in config file
Has a rotator so all logs don't stay locked

## View Logs on a box
```
$ sudo su - sync_gateway
$ ls /home/sync_gateway/logs
```

## Config File
```
  "logFilePath": "string",
  "logging": {
    "default": {
      "logFilePath": "string",
      "logKeys": [
        "string"
      ],
      "logLevel": [
        "string"
      ],
      "rotation": {
        "maxsize": 0,
        "maxage": 0,
        "maxbackups": 0,
        "localtime": false
      }
    }
  },
```
