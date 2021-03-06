# Terraform::OneAndOne::Baremetal

Manages a Baremetal Server on 1&1

## Properties

`Datacenter` - (Optional) Location of desired 1and1 datacenter. Can be `DE`, `GB`, `US` or `ES`.

`Description` - (Optional) Description of the server.

`FirewallPolicyId` - (Optional) ID of firewall policy.

`BaremetalModelId` - (Required) ID of a baremetal model.

`Ip` - (Optional) IP address for the server.

`LoadbalancerId` - (Optional) ID of the load balancer.

`MonitoringPolicyId` - (Optional) ID of monitoring policy.

`Password` - (Optional) Desired password.

`SshKeyPath` - (Optional) Path to private ssh key.

`SshKeyPublic` - (Optional) The public key data in OpenSSH authorized_keys format.

`Id` - (Computed) The ID of the attached IP.

`Ip` - (Computed) The IP.

`FirewallPolicyId` - (Computed) The attached firewall policy.


## See Also

* [oneandone_baremetal](https://www.terraform.io/docs/providers/oneandone/r/baremetal.html) in the _Terraform Provider Documentation_