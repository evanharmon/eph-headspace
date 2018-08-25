# AWS S3
Storage is theoretically unlimited

## General Info
Key / Value Pair
Object based storage - not an OS or Database

## Headers
x-amz-content-sha256
x-amz-date
x-amz-security-token

## Consistency
- read after write consistency for PUTS of new Objects
- eventual consistency for overwrite PUTS and DELETES
(can take some time to propogate)

## Availability
99.99%

## Durability
11 9's - 99.99999999999%

## Concurrent Facility Fault Tolerance
2

## Tiers
S3
S3 - IA
Reduced Redundancy Storage

## Naming Conventions
Names must be lowercase
Universal Namespace (like DNS)

## Limitations
- 100 buckets by default
- PUT limited to 0 Byte to 5GB

## Invalid Bucket Names
capitalization only works in US-Standard-Region US-EAST-1
`.myawsbucket`
`myawsbucket.`
`my..awsbucket`
`myAwsBucket`
