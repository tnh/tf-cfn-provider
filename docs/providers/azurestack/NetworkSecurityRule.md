# Terraform::AzureStack::NetworkSecurityRule

Manages a Network Security Rule.

~> **NOTE on Network Security Groups and Network Security Rules:** Terraform currently
provides both a standalone [Network Security Rule resource](network_security_rule.html), and allows for Network Security Rules to be defined in-line within the [Network Security Group resource](network_security_group.html).
At this time you cannot use a Network Security Group with in-line Network Security Rules in conjunction with any Network Security Rule resources. Doing so will cause a conflict of rule settings and will overwrite rules.

## Properties

`Name` - (Required) The name of the security rule. This needs to be unique across all Rules in the Network Security Group. Changing this forces a new resource to be created.

`ResourceGroupName` - (Required) The name of the resource group in which to create the Network Security Rule. Changing this forces a new resource to be created.

`NetworkSecurityGroupName` - (Required) The name of the Network Security Group that we want to attach the rule to. Changing this forces a new resource to be created.

`Description` - (Optional) A description for this rule. Restricted to 140 characters.

`Protocol` - (Required) Network protocol this rule applies to. Possible values include `Tcp`, `Udp` or `*` (which matches both).

`SourcePortRange` - (Optional) Source Port or Range. Integer or range between `0` and `65535` or `*` to match any.

`DestinationPortRange` - (Optional) Destination Port or Range. Integer or range between `0` and `65535` or `*` to match any.

`SourceAddressPrefix` - (Optional) CIDR or source IP range or * to match any IP. Tags such as ‘VirtualNetwork’, ‘AzureLoadBalancer’ and ‘Internet’ can also be used.

`DestinationAddressPrefix` - (Optional) CIDR or destination IP range or * to match any IP. Tags such as ‘VirtualNetwork’, ‘AzureLoadBalancer’ and ‘Internet’ can also be used.

`Access` - (Required) Specifies whether network traffic is allowed or denied. Possible values are `Allow` and `Deny`.

`Priority` - (Required) Specifies the priority of the rule. The value can be between 100 and 4096. The priority number must be unique for each rule in the collection. The lower the priority number, the higher the priority of the rule.

`Direction` - (Required) The direction specifies if rule will be evaluated on incoming or outgoing traffic. Possible values are `Inbound` and `Outbound`.


## Return Values

### Fn::GetAtt

`Id` - The Network Security Rule ID.

## See Also

* [azurestack_network_security_rule](https://www.terraform.io/docs/providers/azurestack/r/network_security_rule.html) in the _Terraform Provider Documentation_