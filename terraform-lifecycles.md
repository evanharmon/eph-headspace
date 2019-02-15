# TERRAFORM LIFECYCLES

## Summary

Notes on handling timeouts and lifecycle type events with terraform resources

## Timeouts

Handle timeout errors with autoscaling groups
[SO](https://stackoverflow.com/questions/44092511/terraform-autoscaling-group-destroy-timeouts)
[Docs](https://www.terraform.io/docs/configuration/resources.html)

```
timeouts {
	create = "60m"
	delete = "2h"
}
```

## Prevent Resource Destroy

```
lifecycle {
  prevent_destroy = true
}
```
