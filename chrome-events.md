# CHROME EVENTS
(https://developer.chrome.com/devtools/docs/commandline-api)

## Monitor Events On Object
```
monitorEvents(document.body, "click");
monitorEvents(document.body, ["click", "focusout"]);
```

## Stop Monitoring Events On Object
`unmonitorEvents(document.body);`
