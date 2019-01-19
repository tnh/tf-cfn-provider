# Terraform::NSXT::IpSet

This resources provides a way to configure an IP set in NSX. An IP set is a collection of IP addresses. It is often used in the configuration of the NSX firewall.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Id` - ID of the IP set.

`Revision` - Indicates current revision number of the object as seen by NSX-T API server. This attribute can be useful for debugging.

## See Also

* [nsxt_ip_set](https://www.terraform.io/docs/providers/nsxt/r/ip_set.html) in the _Terraform Provider Documentation_