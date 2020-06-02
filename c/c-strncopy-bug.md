# C STRNCOPY BUG

## The Famous Bug
Function does not add a "\0" null byte to the end. This allows it to read
further than the length of the string which is insecure

# Fixes
(https://stackoverflow.com/questions/21210293/problems-with-strncpy-and-how-to-fix-it)
