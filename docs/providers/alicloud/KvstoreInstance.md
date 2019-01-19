# Terraform::Alicloud::KvstoreInstance

Provides an ApsaraDB Redis / Memcache instance resource. A DB instance is an isolated database environment in the cloud. It can be associated with IP whitelists and backup configuration which are separate resource providers.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Id` - The KVStore instance ID.

`ConnectionDomain` - Instance connection domain (only Intranet access supported).

## See Also

* [alicloud_kvstore_instance](https://www.terraform.io/docs/providers/alicloud/r/kvstore_instance.html) in the _Terraform Provider Documentation_