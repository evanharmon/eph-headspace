# SYNC GATEWAY ACCESS

## Share channels via sync function or admin channels
Depends if you need diff ppl to create / approve like banks for example
requireUser()

## Sync Function
can act like validations on updates, etc

you can do try / catch, console.log, etc it's javascript
```
function (doc, oldDoc) {
    if (doc.city === oldDoc.city) { }
}
```

## Sync Function Logging
Be careful of what gets put in logs aka hash if necessary ids like:
- Social Security #'s
- personally identifiable
