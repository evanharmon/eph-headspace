# AWS CLOUDWATCH METRICS

## Aggregate Statistics
- cannot aggregate statistics between regions

## Dimensions On Amazon Default Namespace
leaving out namespace gets statistics for all dimensions

## Dimensions On Custom Namespace
must specify set of dimensions, cannot be blank

## EC2
- detailed monitoring required
- can aggregate by ami

## Custom
- can take up to two minutes for custom metrics to be available on
`get-metric-statistics` command
- can take up to fifteen minutes for custom metrics to be available on
`list-metrics` command

## Publish Zero
- can publish no data or 0 for periods with no associated data.
- if monitoring health with PuMetricData then publish zero
