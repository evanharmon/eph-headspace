# AWS Simple Workflow Service (SWF)
a way to coordinate async and sync tasks
amazon uses it for amazon orders on-line to organize getting the package to you

## SWF vs SQS
SWF retention period is up to 1 year
SQS retention period is 14 days
SWF is a task-oriented API
SQS is message oriented API
SWF a task is assigned only once and is NEVER duplicated
SWF keeps track of all the tasks and events in an application

## Domains
- way to scope separate work flows
- can contain more than one workflow
- workflows in different domains CANNOT talk to each other

## Workflow Starters
Initiates workflow

## Deciders
Control flow of activity tasks in workflow execution - handles failures too

## Activity Workers
carry out the activity tasks
