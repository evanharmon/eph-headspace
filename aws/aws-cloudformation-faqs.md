# AWS CLOUDFORMATION FAQS

## Why can't the LaunchConfigs be in the same file as everything else?
LaunchConfigurations need a dynamic InstanceProfile and SecurityGroups

## Why is an extra stack needed for each autoscaling group?
Have to be in a separate template that accepts parameters

## Why not just use Lambda for LaunchConfig data?
That's a viable option - lambda function could exist in parent stack

## Why have two different security group parameters?
`!Join` does not allow `ImportValue` or `Sub` functions
Imported Values have to be sent as single parameters instead of a list

## Why not separate out instances to separate child stack from parent stack?
It is possible but requires a lot more parameters to be explicitly passed
Part of the reason is the inability of AWS CF to pass Lists to child stacks via
parameters
