# CACHES

## Summary

General info on the topic of Caches

## Resources

- [AWS Caching Challenges && Best Practices](https://aws.amazon.com/builders-library/caching-challenges-and-strategies/?did=ba_card&trk=ba_card)

## Cache Coherence

Cached data can become inconsisent from server to server. Multiple calls can be
returned with different results

## Hard / Soft TTL

During brownouts, clients can be given a response to use cached data up to
Hard TTL and only make requests for items not in local cache.

## In Memory Caches

### Downsides

- Cache Coherence
- Cache is proportional to overall service fleet
- Susceptible to cold starts (empty cache)

## External Caches

### Downsides

- Increased overall system complexity
- additional fleet to monitor, manage, and scale

## Service Code

## Cache Unavailability

- Use in-memory cache as fallback is external cache becomes unavailable

## Inline Caches

Benefits:

- uniform API model to clients
- cache management logic removed from application code

Downsides:

- no opportunity for client to compensate for temporarily unavailable cache

## Monitor

- Cache Hits / Misses
- Total Cache Size
- Number of requests to downstream services
- CPU
- Memory

## Security Vulnerabilities

- poisoning attacks
- side-channel timing attacks
