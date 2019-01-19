# Terraform::VCD::VappVm

Provides a vCloud Director VM resource. This can be used to create,
modify, and delete VMs within a vApp.

~> **Note:** There is known bug with this implementation, that to use the vcd_vapp_vm resource, you must set the paralellism parameter to 1. [We are working on this.](https://github.com/terraform-providers/terraform-provider-vcd/issues/27)

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

## See Also

* [vcd_vapp_vm](https://www.terraform.io/docs/providers/vcd/r/vapp_vm.html) in the _Terraform Provider Documentation_