# Stop and Stop script for a nodejs app
```
script
exec start-stop-daemon --start --make-pidfile --pidfile /var/run/node-app.pid \
     --chuid nodeuser --chdir $APP_DIR \
     --exec /usr/bin/env NODE_ENV=$NODE_ENV PORT=$PORT DEBUG=$DEBUG \
     $NODE_CMD -- $NODE_SCRIPT
end script
```
