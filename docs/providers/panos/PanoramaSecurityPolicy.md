# Terraform::Panos::PanoramaSecurityPolicy

This resource allows you to manage the full security posture.

~> **Note:** `Terraform::Panos::PanoramaSecurityPolicies` is known as `panosPanoramaSecurityPolicy`.

This resource manages the full set of security rules, enforcing both the
contents of individual rules as well as their ordering.  Rules are defined in
a `Rule` config block.  As this manages the full set of security rules for
a given rulebase, any extraneous rules are removed on `terraform apply`.

For each security rule, there are three styles of profile settings:

* `None` (the default)
* `Group`
* `Profiles`

The Profile Setting is implicitly chosen based on what params are configured
for the security rule.  If you want a Profile Setting of `Group`, then the
`Group` param should be set to the desired Group Profile.  If you want a
Profile Setting of `Profiles`, then you will need to specify one or more of
the following params:

* `Virus`
* `Spyware`
* `Vulnerability`
* `UrlFiltering`
* `FileBlocking`
* `WildfireAnalysis`
* `DataFiltering`

If the `Group` param and none of the `Profiles` params are specified, then
the Profile Setting is set to `None`.

## Properties

`DeviceGroup` - (Optional) The device group to put the security policy into
(default: `shared`).

`Rulebase` - (Optional) The rulebase.  This can be `pre-rulebase` (default),
`post-rulebase`, or `Rulebase`.

`Rule` - The security rule definition (see below).  The security rule
ordering will match how they appear in the terraform plan file.

### Rule Properties

`Name` - (Required) The security rule name.

`Type` - (Optional) Rule type.  This can be `universal` (default),
`interzone`, or `intrazone`.

`Description` - (Optional) The description.

`Tags` - (Optional) List of tags for this security rule.

`SourceZones` - (Required) List of source zones.

`SourceAddresses` - (Required) List of source addresses.

`NegateSource` - (Optional, bool) If the source should be negated.

`SourceUsers` - (Required) List of source users.

`HipProfiles` - (Required) List of HIP profiles.

`DestinationZones` - (Required) List of destination zones.

`DestinationAddresses` - (Required) List of destination addresses.

`NegateDestination` - (Optional, bool) If the destination should be negated.

`Applications` - (Required) List of applications.

`Services` - (Required) List of services.

`Categories` - (Required) List of categories.

`Action` - (Optional) Action for the matched traffic.  This can be `allow`
(default), `deny`, `drop`, `reset-client`, `reset-server`, or `reset-both`.

`LogSetting` - (Optional) Log forwarding profile.

`LogStart` - (Optional, bool) Log the start of the traffic flow.

`LogEnd` - (Optional, bool) Log the end of the traffic flow (default: `true`).

`Disabled` - (Optional, bool) Set to `true` to disable this rule.

`Schedule` - (Optional) The security rule schedule.

`IcmpUnreachable` - (Optional) Set to `true` to enable ICMP unreachable.

`DisableServerResponseInspection` - (Optional) Set to `true` to disable
server response inspection.

`Group` - (Optional) Profile Setting: `Group` - The group profile name.

`Virus` - (Optional) Profile Setting: `Profiles` - The antivirus setting.

`Spyware` - (Optional) Profile Setting: `Profiles` - The anti-spyware
setting.

`Vulnerability` - (Optional) Profile Setting: `Profiles` - The Vulnerability
Protection setting.

`UrlFiltering` - (Optional) Profile Setting: `Profiles` - The URL filtering
setting.

`FileBlocking` - (Optional) Profile Setting: `Profiles` - The file blocking
setting.

`WildfireAnalysis` - (Optional) Profile Setting: `Profiles` - The WildFire
Analysis setting.

`DataFiltering` - (Optional) Profile Setting: `Profiles` - The Data
Filtering setting.

`Target` - (Optional) A target definition (see below).  If there are no
target sections, then the rule will apply to every vsys of every device
in the device group.

`NegateTarget` - (Optional, bool) Instead of applying the rule for the
given serial numbers, apply it to everything except them.

### Target Properties

`Serial` - (Required) The serial number of the firewall.

`VsysList` - (Optional) A subset of all available vsys on the firewall
that should be in this device group.  If the firewall is a virtual firewall,
then this parameter should just be omitted.


## See Also

* [panos_panorama_security_policy](https://www.terraform.io/docs/providers/panos/r/panorama_security_policy.html) in the _Terraform Provider Documentation_