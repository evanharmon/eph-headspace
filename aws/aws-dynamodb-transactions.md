# AWS DYNAMODB TRANSACTIONS

## Summary

Notes on doing transactions in DynamoDB

## Resources

- [AWS Blog On DynamoDB Transactions](https://aws.amazon.com/blogs/aws/new-amazon-dynamodb-transactions/)
- [AWS Docs](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/transactions.html)
- [Appsync Support](https://aws.amazon.com/blogs/mobile/appsync-caching-transactions/)

### Limitations

- global tables not supported

### Tables

- transactions support multiple tables

### Locking

Items are not locked - an edit on an item will abort the transaction

```
DynamoDB transactions provide serializable isolation. If an item is modified
outside of a transaction while the transaction is in progress, the transaction
is canceled and an exception is thrown with details about which item or items
caused the exception.
```
