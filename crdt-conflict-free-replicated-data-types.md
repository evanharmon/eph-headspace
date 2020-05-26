# CONFLICT RESOLUTION SEMANTICS

## Summary

notes on managing conflicts with CRDT data types

## Resources

- [CRDT Paper By Nuno Preguica](https://arxiv.org/pdf/1805.06358.pdf)

### Concurrency Semantics

#### Happens-Before

##### Add-Wins Set

`add` trumps previous `remove` and document still exists
