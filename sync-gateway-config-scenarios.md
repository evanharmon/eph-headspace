# SYNC GATEWAY CONFIG SCENARIOS

## Sync Function Change without Resync
Steps:
- Write document without new property like 'doctype.myState'
- Change Sync function in config
- Stop / Start sync gateway on the box or full container
- Observe: All previous docs, which may fail new sync function, have not been
  processed and are left with their channel
- Observe: New sync function operates successfully on new writes

## Sync Function Change With Resync
Steps:
- Write document without new property like 'doctype.myState'
- Change Sync function in config
- Stop / Start sync gateway on the box or full container
- Observe: All previous docs, which may fail new sync function, have not been
  processed and are left with their channel
- Observe: New sync function operates successfully on new writes
- Take bucket offline, resync
- Observe: previous docs that fail new sync function show errors in SG logs and
  have channels REMOVED
- Observe: _changes feed will show previous docs with their channels shown as
  'removed'
- Observe: document is listed in changes feed for that channel with 'removed',
  and if you do active_only=true then it will not be shown
