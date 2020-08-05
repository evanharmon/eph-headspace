# CONFLICT FREE REPLICATED DATA TYPE (CRDT)

## Summary

notes on managing conflicts in data on applications

## Resources

- [Conflict Free Replicated Data Type](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type)
- [CRDT Website](https://crdt.tech/)
- [CRDT Paper By Nuno Preguica](https://arxiv.org/pdf/1805.06358.pdf)

### CRDT

- multi-user from the ground up

### Problems Solved by CRDT

#### Last Write Wins

Stale updates may win!

- unstable connection
- network latency
- unreliable clocks

### Merge Function

Use the same merge function / code across client, server, and data store!
