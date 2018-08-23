# AWS S3 VERSIONING LIFECYCLE
versioning Integrates with Lifecycle rules
versioning Supports MFA Delete capability

## Limitations
- versioning Can not be turned off, can only be suspended
- lifecycle Mgmt policies cannot move to RRS
- expire does not delete - just adds delete marker

### Deduplication
- no de-duplication like GIT, so costs can get high
- every file has it's own version ID

## Transitions

### S3 to S3 IA
Minimum is 30 day's after creation
Minimum size 128kb

### Archive to Glacier
Minimum is 60 day's after creation

### Permanently Delete
Minimum is 1 day after Glacier archive
