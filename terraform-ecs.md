# TERRAFORM ECS

## Summary

Notes on using terraform with AWS ECS

## Error Decoding JSON

Task definition expects a container definition like below.
NOT a full task definition. The task definition parts are filled out
in that resource as addtl properties not a rendered json

## Disallowed Properties In Container Definitions

network_mode
volumesFrom
cpu
memory
task_role_arn
execution_role_arn
