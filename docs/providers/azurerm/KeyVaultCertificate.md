# Terraform::AzureRM::KeyVaultCertificate

Manages a Key Vault Certificate.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Id` - The Key Vault Certificate ID.

`SecretId` - The ID of the associated Key Vault Secret.

`Version` - The current version of the Key Vault Certificate.

`CertificateData` - The raw Key Vault Certificate.

`Thumbprint` - The X509 Thumbprint of the Key Vault Certificate returned as hex string.

## See Also

* [azurerm_key_vault_certificate](https://www.terraform.io/docs/providers/azurerm/r/key_vault_certificate.html) in the _Terraform Provider Documentation_