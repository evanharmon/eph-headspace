# CURL

## Send Post with Form Data
remember to URL encode with % symbols where necessary
`$ curl --data "param1=value1&param2=value2" https://example.com/resource.cgi`

## Send Post Multi-part Form
```
$ curl \
    --form "fileupload=@my-file.txt;filename=desired-filename.txt" \
    --form param1=value1 \
    --form param2=value2 \
    https://example.com/resource.cgi
```

## Follow redirects
`$ curl -L`

## Save as File
`$ curl -o "file.txt" https://example.com/file`

## Insecure mode
`$ curl -k`

## Custom Request Method / POST data
`$ curl -XPOST -d'{"s":"hello, world"}' localhost:8080/uppercase`

## JSON data as payload
```
$ curl -vX POST \
    http://server/api/v1/places.json \
    -d @testplace.json \
    --header "Content-Type: application/json"
```

## spoof a referer
```
$ curl -v \
    http://example-bucket.s3.amazonaws.com/secret-image.jpg \
    -H 'Referer: http://example.com/good-guy.html'
```

## Use basic auth
`$ curl -v -u Administrator:password localhost:8091`

## Show timings
(https://blog.josephscott.org/2011/10/14/timing-details-with-curl/)
Step 1: Create File
```
time_namelookup: %{time_namelookup}\n
time_connect: %{time_connect}\n
time_appconnect: %{time_appconnect}\n
time_pretransfer: %{time_pretransfer}\n
time_redirect: %{time_redirect}\n
time_starttransfer: %{time_starttransfer}\n
----------\n
time_total: %{time_total}\n
```
Step 2: make curl
`$ curl -w "@curl-format.txt" -s "http://wordpress.com/"`

## Use ENV Variables In Curl
shell does not expand env vars in single quotes - have to use double
```
$ curl -u <my-api-token>: \
  -X POST https://api.pushbullet.com/v2/pushes \
  --header 'Content-Type: application/json' \
  --data-binary '{"type": "note", "title": "'"$TR_TORRENT_NAME"'", \
  "body": "'"$TR_TORRENT_NAME completed"'."}'
```

## Use ENV Variables In Curl Without Double Quoting
`$ curl -u <my-api-token>: -H 'Content-Type: '$TYPE''`
