# AWS S3 VERSIONING LIFECYCLE
versioning integrates with lifecycle rules
versioning supports MFA delete capability

## Limitations
- versioning can not be turned off, can only be suspended
- lifecycle management policies cannot move to RRS
- expire does not delete - just adds delete marker

### Deduplication
- no de-duplication like GIT, so costs can get high
- every file has it's own version ID

## Transitions
Archive to Infrequently accessed then Glacier or straight to Glacier

### S3 to S3 IA
Minimum is 30 day's after creation
Minimum size 128kb

### Archive to Glacier
Minimum is 60 day's after creation

### Permanently Delete
Minimum is 1 day after Glacier archive
