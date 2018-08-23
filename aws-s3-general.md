# AWS S3
Storage is theoretically unlimited

## General Info
Key / Value Pair
Object based storage - not an OS or Database
Uploads are private by default

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

## Limited To 100 Buckets By Default
Can submit a service limit increase for more

### File Size Limits
PUT limited to 0 Byte to 5GB

## Invalid Bucket Names
`.myawsbucket`
`myawsbucket.`
`my..awsbucket`
`myAwsBucket` ## capitalization only works in US-Standard-Region US-EAST-1
