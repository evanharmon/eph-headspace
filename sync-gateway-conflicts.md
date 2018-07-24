# SYNC GATEWAY CONFLICTS

## Deterministic
highest rev wins

## Check Conflicts
`localhost:4984/sync_gateway/_changes?active_only=true&style=all_docs`

## GET Conflicts in Body Map
`localhost:4985/sync_gateway/_raw/foo`

## Fix Conflicts
- PUT with correct document
- Clean up Branches with delete actions on the conflict versions to trash

### Bulk Delete
`DELETE localhost:4984/sync_gateway/foo?rev=1-123&rev=1-456`

## Get conflicts in batches
use the limit feed `limit=100`

## Collaboration Ideas / Tips
CouchLite and Manager Have to Use Same Logic

### Collaboration Documents
Is it a collaborative document? Is it not collaborative?
Maybe only one person needs to access

### Collaboration Document Conflicts
if you let users / programs handle conflicts, they usually won't, and it will
just grow grow grow and bomb out your SG

## Potential Conflict Scenarios
On Modifications / Updates / Soft Deletes, the rev_id is required. This is
where a highly available environment could create conflicts. Situation is where
one instance of microservice 1 grabs changes feed with rev_id, and makes update.
Another service grabs same record, same rev_id and tries to make an update. The
rev_id is now different after microservice 1 finishes. This creates a conflict
as the 2nd microservice rev_id is old

## Multi Version Concurrency Control
(https://blog.couchbase.com/conflict-resolution-couchbase-mobile/)
Couchbase Mobile uses the Multi Version Concurrency Control (MVCC) technique to
handle conflicts. In this method, every document is assigned a unique system
generated revision ID. This ID is in addition to the document ID which remains
the same across document revisions. Every change to a document, be it is a
modification or a delete is treated as a new revision to the document and is
hence, assigned a new revision ID

## Conflicts are Determined by Couchbase Document Id/Revision Id
not the contents of a document
