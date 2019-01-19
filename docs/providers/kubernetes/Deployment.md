# Terraform::Kubernetes::Deployment

A Deployment ensures that a specified number of pod “replicas” are running at any one time. In other words, a Deployment makes sure that a pod or homogeneous set of pods are always up and available. If there are too many pods, it will kill some. If there are too few, the Deployment will start more.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

## See Also

* [kubernetes_deployment](https://www.terraform.io/docs/providers/kubernetes/r/deployment.html) in the _Terraform Provider Documentation_