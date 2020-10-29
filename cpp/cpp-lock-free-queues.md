# CPP LOCK FREE QUEUES

## Summary

Notes on lock free queues and multi-threaded programming

## Resources

- [Herb Sutter Articles](https://herbsutter.com/2008/11/02/out-of-order-effective-concurrency-writing-lock-free-code-a-corrected-queue/)

### Lock Free Variables

must avoid race conditions. Key properties to observe and guarantee:

- atomicity
- ordering

guidelines:

- limit size to native word size
- use pointers
