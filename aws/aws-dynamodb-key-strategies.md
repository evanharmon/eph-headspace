# AWS DYNAMODB KEY STRATEGIES

## Summary

Notes on efficient (or not efficient) key strategies for DynamoDB

## Resources

- [Sort Keys Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-sort-keys.html)
- [Overloading GSI](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-gsi-overloading.html)

## Composite Sort Keys For One

#### One To Many Relationships

[country]#[region]#[state]#[county]#[city]#[neighborhood]
