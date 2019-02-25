## TERRAFORM VPNS

## Summary

Notes on managing AWS VPNs with terraform

## VPN Connections

#### aws_vpn_connection_route

For VPN connections that already exist, static routes cannot be `imported` in
to Terraform.

To fully import the static routes tied to the aws_vpn_connection, do a
`terraform apply tfplan` with the same routes as listed in the AWS console for
the VPN Connection. This won't create duplicate routes, it will just match up the
state correctly.
