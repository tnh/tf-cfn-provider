# Terraform::Vault::ApproleAuthBackendLogin

Logs into Vault using the AppRole auth backend. See the [Vault
documentation](https://www.vaultproject.io/docs/auth/approle.html) for more
information.

## Properties

`RoleId` - (Required) The ID of the role to log in with.

`SecretId` - (Optional) The secret ID of the role to log in with. Required
unless `bind_secret_id` is set to false on the role.

`Backend` - The unique path of the Vault backend to log in with.


## Return Values

### Fn::GetAtt

`Policies` - A list of policies applied to the token.

`Renewable` - Whether the token is renewable or not.

`LeaseDuration` - How long the token is valid for, in seconds.

`LeaseStarted` - The date and time the lease started, in RFC 3339 format.

`Accessor` - The accessor for the token.

`ClientToken` - The Vault token created.

`Metadata` - The metadata associated with the token.

## See Also

* [vault_approle_auth_backend_login](https://www.terraform.io/docs/providers/vault/r/approle_auth_backend_login.html) in the _Terraform Provider Documentation_