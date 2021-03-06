# Terraform::VSphere::ComputeClusterVmGroup

The `Terraform::VSphere::ComputeClusterVmGroup` resource can be used to manage groups of
virtual machines in a cluster, either created by the
[`Terraform::VSphere::ComputeCluster`][tf-vsphere-cluster-resource] resource or looked up
by the [`Terraform::VSphere::ComputeCluster`][tf-vsphere-cluster-data-source] data source.

[tf-vsphere-cluster-resource]: /docs/providers/vsphere/r/compute_cluster.html
[tf-vsphere-cluster-data-source]: /docs/providers/vsphere/d/compute_cluster.html

This resource mainly serves as an input to the
[`Terraform::VSphere::ComputeClusterVmDependencyRule`][tf-vsphere-cluster-vm-dependency-rule-resource]
and
[`Terraform::VSphere::ComputeClusterVmHostRule`][tf-vsphere-cluster-vm-host-rule-resource]
resources. See the individual resource documentation pages for more information.

[tf-vsphere-cluster-vm-dependency-rule-resource]: /docs/providers/vsphere/r/compute_cluster_vm_dependency_rule.html
[tf-vsphere-cluster-vm-host-rule-resource]: /docs/providers/vsphere/r/compute_cluster_vm_host_rule.html

~> **NOTE:** This resource requires vCenter and is not available on direct ESXi
connections.

~> **NOTE:** vSphere DRS requires a vSphere Enterprise Plus license.

## Properties

`Name` - (Required) The name of the VM group. This must be unique in the
cluster. Forces a new resource if changed.

`ComputeClusterId` - (Required) The [managed object reference
ID][docs-about-morefs] of the cluster to put the group in.  Forces a new
resource if changed.

`VirtualMachineIds` - (Required) The UUIDs of the virtual machines in this
group.


## See Also

* [vsphere_compute_cluster_vm_group](https://www.terraform.io/docs/providers/vsphere/r/compute_cluster_vm_group.html) in the _Terraform Provider Documentation_