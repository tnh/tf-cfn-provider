# Terraform::OPC::ComputeRoute

The `Terraform::OPC::ComputeRoute` resource creates and manages a route for an IP Network in an Oracle Cloud Infrastructure Compute Classic identity domain.

## Properties

`Name` - (Required) The name of the route.

`Description` - (Optional) The description of the route.

`AdminDistance` - (Optional) The route's administrative distance. Defaults to `0`.

`IpAddressPrefix` - (Required) The IPv4 address prefix, in CIDR format, of the external network from which to route traffic.

`NextHopVnicSet` - (Required) Name of the virtual NIC set to route matching packets to. Routed flows are load-balanced among all the virtual NICs in the virtual NIC set.


## Return Values

### Fn::GetAtt

`Description` - The description of the route.

`AdminDistance` - The route's administrative distance. Defaults to `0`.

`IpAddressPrefix` - The IPv4 address prefix, in CIDR format, of the external network from which to route traffic.

`NextHopVnicSet` - Name of the virtual NIC set to route matching packets to. Routed flows are load-balanced among all the virtual NICs in the virtual NIC set.

## See Also

* [opc_compute_route](https://www.terraform.io/docs/providers/opc/r/compute_route.html) in the _Terraform Provider Documentation_