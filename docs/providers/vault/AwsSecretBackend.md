# Terraform::Vault::AwsSecretBackend

Creates an AWS Secret Backend for Vault. AWS secret backends can then issue AWS
access keys and secret keys, once a role has been added to the backend.

~> **Important** All data provided in the resource configuration will be
written in cleartext to state and plan files generated by Terraform, and
will appear in the console output when Terraform runs. Protect these
artifacts accordingly. See
[the main provider documentation](../index.html)
for more details.

## Properties

`AccessKey` - (Required) The AWS Access Key ID this backend should use to
issue new credentials.

`SecretKey` - (Required) The AWS Secret Key this backend should use to
issue new credentials.

`Region` - (Optional) The AWS region for API calls. Defaults to `us-east-1`.

`Path` - (Optional) The unique path this backend should be mounted at. Must
not begin or end with a `/`. Defaults to `aws`.

`Description` - (Optional) A human-friendly description for this backend.

`DefaultLeaseTtlSeconds` - (Optional) The default TTL for credentials
issued by this backend.

`MaxLeaseTtlSeconds` - (Optional) The maximum TTL that can be requested
for credentials issued by this backend.


## See Also

* [vault_aws_secret_backend](https://www.terraform.io/docs/providers/vault/r/aws_secret_backend.html) in the _Terraform Provider Documentation_