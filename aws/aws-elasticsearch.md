# AWS ELASTIC SEARCH

## Upload data via CURL
/usersdata/ represents index
```
$ curl -XPOST \
    --data-binary @bulk_movies.json \
    'http://search-movies-hash.us-west-1.es.amazonaws.com/usersdata/_bulk'
```

## Search via CURL
/usersdata/ represents index
```
$ curl \
    'https://search-eh-elasticsearch-hash.us-east-1.es.amazonaws.com/usersdata/_search?q=*&pretty'
```

## Mapping
- create elastic search records AFTER mapping is created... otherwise
- you will chase your tail wondering how you got non-nested mappings for a new
index

## Search All Docs Across All Types Within An Index
`$ curl -XGET 'http://localhost:9200/twitter/_search?q=user:kimchy'`

## Search Within Specific Type
`$ curl -XGET 'http://localhost:9200/twitter/tweet,user/_search?q=user:kimchy'`
