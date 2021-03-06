# Terraform::NSXT::FirewallSection

This resource provides a way to configure a firewall section on the NSX manager. A firewall section is a collection of firewall rules that are grouped together.

## Properties

`DisplayName` - (Optional) The display name of this firewall section. Defaults to ID if not set.

`Description` - (Optional) Description of this firewall section.

`Tag` - (Optional) A list of scope + tag pairs to associate with this firewall section.

`AppliedTo` - (Optional) List of objects where the rules in this section will be enforced. This will take precedence over rule level applied_to. [Supported target types: "LogicalPort", "LogicalSwitch", "NSGroup"].

`SectionType` - (Required) Type of the rules which a section can contain. Either LAYER2 or LAYER3. Only homogeneous sections are supported.

`Stateful` - (Required) Stateful or Stateless nature of firewall section is enforced on all rules inside the section. Layer3 sections can be stateful or stateless. Layer2 sections can only be stateless.

`Rule` - (Optional) A list of rules to be applied in this section. each rule has the following arguments:
* `DisplayName` - (Optional) The display name of this rule. Defaults to ID if not set.
* `Description` - (Optional) Description of this rule.
* `Action` - (Required) Action enforced on the packets which matches the firewall rule. [Allowed values: "ALLOW", "DROP", "REJECT"]
* `AppliedTo` - (Optional) List of objects where rule will be enforced. The section level field overrides this one. Null will be treated as any. [Supported target types: "LogicalPort", "LogicalSwitch", "NSGroup"]
* `Destination` - (Optional) List of the destinations. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `DestinationsExcluded` - (Optional) When this boolean flag is set to true, the rule destinations will be negated.
* `Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`DisplayName` - (Optional) The display name of this rule. Defaults to ID if not set.
* `Description` - (Optional) Description of this rule.
* `Action` - (Required) Action enforced on the packets which matches the firewall rule. [Allowed values: "ALLOW", "DROP", "REJECT"]
* `AppliedTo` - (Optional) List of objects where rule will be enforced. The section level field overrides this one. Null will be treated as any. [Supported target types: "LogicalPort", "LogicalSwitch", "NSGroup"]
* `Destination` - (Optional) List of the destinations. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `DestinationsExcluded` - (Optional) When this boolean flag is set to true, the rule destinations will be negated.
* `Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Description` - (Optional) Description of this rule.
* `Action` - (Required) Action enforced on the packets which matches the firewall rule. [Allowed values: "ALLOW", "DROP", "REJECT"]
* `AppliedTo` - (Optional) List of objects where rule will be enforced. The section level field overrides this one. Null will be treated as any. [Supported target types: "LogicalPort", "LogicalSwitch", "NSGroup"]
* `Destination` - (Optional) List of the destinations. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `DestinationsExcluded` - (Optional) When this boolean flag is set to true, the rule destinations will be negated.
* `Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Action` - (Required) Action enforced on the packets which matches the firewall rule. [Allowed values: "ALLOW", "DROP", "REJECT"]
* `AppliedTo` - (Optional) List of objects where rule will be enforced. The section level field overrides this one. Null will be treated as any. [Supported target types: "LogicalPort", "LogicalSwitch", "NSGroup"]
* `Destination` - (Optional) List of the destinations. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `DestinationsExcluded` - (Optional) When this boolean flag is set to true, the rule destinations will be negated.
* `Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`AppliedTo` - (Optional) List of objects where rule will be enforced. The section level field overrides this one. Null will be treated as any. [Supported target types: "LogicalPort", "LogicalSwitch", "NSGroup"]
* `Destination` - (Optional) List of the destinations. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `DestinationsExcluded` - (Optional) When this boolean flag is set to true, the rule destinations will be negated.
* `Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Destination` - (Optional) List of the destinations. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `DestinationsExcluded` - (Optional) When this boolean flag is set to true, the rule destinations will be negated.
* `Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`DestinationsExcluded` - (Optional) When this boolean flag is set to true, the rule destinations will be negated.
* `Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Direction` - (Optional) Rule direction in case of stateless firewall rules. This will only considered if section level parameter is set to stateless. Default to IN_OUT if not specified. [Allowed values: "IN", "OUT", "IN_OUT"]
* `Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Disabled` - (Optional) Flag to disable rule. Disabled will only be persisted but never provisioned/realized.
* `IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`IpProtocol` - (Optional) Type of IP packet that should be matched while enforcing the rule. [allowed values: "IPV4", "IPV6", "IPV4_IPV6"]
* `Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Logged` - (Optional) Flag to enable packet logging. Default is disabled.
* `Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Notes` - (Optional) User notes specific to the rule.
* `RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`RuleTag` - (Optional) User level field which will be printed in CLI and packet logs.
* `Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Service` - (Optional) List of the services. Null will be treated as any. [Allowed target types: "NSService", "NSServiceGroup"]
* `Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`Source` - (Optional) List of sources. Null will be treated as any. [Allowed target types: "IPSet", "LogicalPort", "LogicalSwitch", "NSGroup", "MACSet" (depending on the section type)]
* `SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.

`SourcesExcluded` - (Optional) When this boolean flag is set to true, the rule sources will be negated.


## Return Values

### Fn::GetAtt

`Id` - ID of the firewall section.

`Revision` - Indicates current revision number of the object as seen by NSX-T API server. This attribute can be useful for debugging.

`IsDefault` - A boolean flag which reflects whether a firewall section is default section or not. Each Layer 3 and Layer 2 section will have at least and at most one default section.

## See Also

* [nsxt_firewall_section](https://www.terraform.io/docs/providers/nsxt/r/firewall_section.html) in the _Terraform Provider Documentation_