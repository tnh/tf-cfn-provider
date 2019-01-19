# Terraform::FlexibleEngine::NetworkingSecgroupV2

Manages a V2 neutron security group resource within FlexibleEngine.
Unlike Nova security groups, neutron separates the group from the rules
and also allows an admin to target a specific tenant_id.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Region` - See Argument Reference above.

`Name` - See Argument Reference above.

`Description` - See Argument Reference above.

`TenantId` - See Argument Reference above.

## See Also

* [flexibleengine_networking_secgroup_v2](https://www.terraform.io/docs/providers/flexibleengine/r/networking_secgroup_v2.html) in the _Terraform Provider Documentation_