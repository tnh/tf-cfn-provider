# Terraform::Kubernetes::PersistentVolume

The resource provides a piece of networked storage in the cluster provisioned by an administrator. It is a resource in the cluster just like a node is a cluster resource. Persistent Volumes have a lifecycle independent of any individual pod that uses the PV.

For more info see [Kubernetes reference](https://kubernetes.io/docs/concepts/storage/persistent-volumes)/

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

## See Also

* [kubernetes_persistent_volume](https://www.terraform.io/docs/providers/kubernetes/r/persistent_volume.html) in the _Terraform Provider Documentation_