# Terraform::AzureStack::VirtualMachineScaleSet

Manages a virtual machine scale set.

~> **Note:** All arguments including the administrator login and password will be stored in the raw state as plain-text.
[Read more about sensitive data in state](/docs/state/sensitive-data.html).

## Properties

`Name` - (Required) Specifies the name of the virtual machine scale set resource. Changing this forces a new resource to be created.

`ResourceGroupName` - (Required) The name of the resource group in which to create the virtual machine scale set. Changing this forces a new resource to be created.

`Location` - (Required) Specifies the supported Azure location where the resource exists. Changing this forces a new resource to be created.

`Sku` - (Required) A sku block as documented below.

`UpgradePolicyMode` - (Required) Specifies the mode of an upgrade to virtual machines in the scale set. Possible values, `Manual` or `Automatic`.

`Overprovision` - (Optional) Specifies whether the virtual machine scale set should be overprovisioned. Defaults to `true`.

`LicenseType` - (Optional, when a Windows machine) Specifies the Windows OS license type. If supplied, the only allowed values are `Windows_Client` and `Windows_Server`.

`OsProfile` - (Required) A Virtual Machine OS Profile block as documented below.

`OsProfileSecrets` - (Optional) A collection of Secret blocks as documented below.

`OsProfileWindowsConfig` - (Required, when a windows machine) A Windows config block as documented below.

`OsProfileLinuxConfig` - (Required, when a linux machine) A Linux config block as documented below.

`NetworkProfile` - (Required) A collection of network profile block as documented below.

`StorageProfileOsDisk` - (Required) A storage profile os disk block as documented below.

`StorageProfileImageReference` - (Optional) A storage profile image reference block as documented below.

`Extension` - (Optional) Can be specified multiple times to add extension profiles to the scale set. Each `Extension` block supports the fields documented below.

`Plan` - (Optional) A plan block as documented below.

`Priority` - (Optional) Specifies the priority for the virtual machines in the scale set, defaults to `Regular`. Possible values are `Low` and `Regular`.

`Tags` - (Optional) A mapping of tags to assign to the resource.

### Sku Properties

`Name` - (Required) Specifies the size of virtual machines in a scale set.

`Tier` - (Optional) Specifies the tier of virtual machines in a scale set. Possible values, `standard` or `basic`.

`Capacity` - (Required) Specifies the number of virtual machines in the scale set.

`Type` - (Required) Specifies the identity type to be assigned to the scale set. The only allowable value is `SystemAssigned`. To enable Managed Service Identity (MSI) on all machines in the scale set, an extension with the type "ManagedIdentityExtensionForWindows" or "ManagedIdentityExtensionForLinux" must also be added. The scale set's Service Principal ID (SPN) can be retrieved after the scale set has been created.

### OsProfile Properties

`ComputerNamePrefix` - (Required) Specifies the computer name prefix for all of the virtual machines in the scale set. Computer name prefixes must be 1 to 9 characters long for windows images and 1 - 58 for linux. Changing this forces a new resource to be created.

`AdminUsername` - (Required) Specifies the administrator account name to use for all the instances of virtual machines in the scale set.

`AdminPassword` - (Required) Specifies the administrator password to use for all the instances of virtual machines in a scale set.

`CustomData` - (Optional) Specifies custom data to supply to the machine. On linux-based systems, this can be used as a cloud-init script. On other systems, this will be copied as a file on disk. Internally, Terraform will base64 encode this value before sending it to the API. The maximum length of the binary array is 65535 bytes.

### OsProfileSecrets Properties

`SourceVaultId` - (Required) Specifies the key vault to use.

`VaultCertificates` - (Required, on windows machines) A collection of Vault Certificates as documented below.

### VaultCertificates Properties

`CertificateUrl` - (Required) It is the Base64 encoding of a JSON Object that which is encoded in UTF-8 of which the contents need to be `data`, `dataType` and `password`.

`CertificateStore` - (Required, on windows machines) Specifies the certificate store on the Virtual Machine where the certificate should be added to.

### OsProfileWindowsConfig Properties

`ProvisionVmAgent` - (Optional) Indicates whether virtual machine agent should be provisioned on the virtual machines in the scale set.

`EnableAutomaticUpgrades` - (Optional) Indicates whether virtual machines in the scale set are enabled for automatic updates.

`Winrm` - (Optional) A collection of WinRM configuration blocks as documented below.

`AdditionalUnattendConfig` - (Optional) An Additional Unattended Config block as documented below.

### Winrm Properties

`Protocol` - (Required) Specifies the protocol of listener.

`CertificateUrl` - (Optional) Specifies URL of the certificate with which new Virtual Machines is provisioned.

### AdditionalUnattendConfig Properties

`Pass` - (Required) Specifies the name of the pass that the content applies to. The only allowable value is `oobeSystem`.

`Component` - (Required) Specifies the name of the component to configure with the added content. The only allowable value is `Microsoft-Windows-Shell-Setup`.

`SettingName` - (Required) Specifies the name of the setting to which the content applies. Possible values are: `FirstLogonCommands` and `AutoLogon`.

`Content` - (Optional) Specifies the base-64 encoded XML formatted content that is added to the unattend.xml file for the specified path and component.

### OsProfileLinuxConfig Properties

`DisablePasswordAuthentication` - (Required) Specifies whether password authentication should be disabled. Changing this forces a new resource to be created.

`SshKeys` - (Optional) Specifies a collection of `path` and `key_data` to be placed on the virtual machine.

### NetworkProfile Properties

`Name` - (Required) Specifies the name of the network interface configuration.

`Primary` - (Required) Indicates whether network interfaces created from the network interface configuration will be the primary NIC of the VM.

`IpConfiguration` - (Required) An ip_configuration block as documented below.

`Name` - (Required) The name of the public ip address configuration.

`IdleTimeout` - (Required) The idle timeout in minutes. This value must be between 4 and 32.

`DomainNameLabel` - (Required) The domain name label for the dns settings.

### StorageProfileOsDisk Properties

`Name` - (Optional) Specifies the disk name. Must be specified when using unmanaged disk ('managed_disk_type' property not set).

`VhdContainers` - (Optional) Specifies the vhd uri. Cannot be used when `Image` or `ManagedDiskType` is specified.

`ManagedDiskType` - (Optional) Specifies the type of managed disk to create. Value you must be either `Standard_LRS` or `Premium_LRS`. Cannot be used when `VhdContainers` or `Image` is specified.

`CreateOption` - (Required) Specifies how the virtual machine should be created. The only possible option is `FromImage`.

`Caching` - (Optional) Specifies the caching requirements. Possible values include: `None` (default), `ReadOnly`, `ReadWrite`.

`Image` - (Optional) Specifies the blob uri for user image. A virtual machine scale set creates an os disk in the same container as the user image.
Updating the osDisk image causes the existing disk to be deleted and a new one created with the new image. If the VM scale set is in Manual upgrade mode then the virtual machines are not updated until they have manualUpgrade applied to them.
When setting this field `OsType` needs to be specified.

`OsType` - (Optional) Specifies the operating system Type, valid values are windows, linux.

`Lun` - (Required) Specifies the Logical Unit Number of the disk in each virtual machine in the scale set.

`CreateOption` - (Optional) Specifies how the data disk should be created. The only possible options are `FromImage` and `Empty`.

`Caching` - (Optional) Specifies the caching requirements. Possible values include: `None` (default), `ReadOnly`, `ReadWrite`.

`DiskSizeGb` - (Optional) Specifies the size of the disk in GB. This element is required when creating an empty disk.

### StorageProfileImageReference Properties

`Id` - (Optional) Specifies the ID of the (custom) image to use to create the virtual
machine scale set, as in the [example below](#example-of-storage_profile_image_reference-with-id).

`Publisher` - (Optional) Specifies the publisher of the image used to create the virtual machines.

`Offer` - (Optional) Specifies the offer of the image used to create the virtual machines.

`Sku` - (Optional) Specifies the SKU of the image used to create the virtual machines.

`Version` - (Optional) Specifies the version of the image used to create the virtual machines.

### Extension Properties

`Name` - (Required) Specifies the name of the extension.

`Publisher` - (Required) The publisher of the extension, available publishers can be found by using the Azure CLI.

`Type` - (Required) The type of extension, available types for a publisher can be found using the Azure CLI.

`TypeHandlerVersion` - (Required) Specifies the version of the extension to use, available versions can be found using the Azure CLI.

`AutoUpgradeMinorVersion` - (Optional) Specifies whether or not to use the latest minor version available.

`Settings` - (Required) The settings passed to the extension, these are specified as a JSON object in a string.

`ProtectedSettings` - (Optional) The protected_settings passed to the extension, like settings, these are specified as a JSON object in a string.

### Plan Properties

`Name` - (Required) Specifies the name of the image from the marketplace.

`Publisher` - (Required) Specifies the publisher of the image.

`Product` - (Required) Specifies the product of the image from the marketplace.


## Return Values

### Fn::GetAtt

`Id` - The virtual machine scale set ID.

`BootDiagnostics` - A boot diagnostics profile block as referenced below.

## See Also

* [azurestack_virtual_machine_scale_set](https://www.terraform.io/docs/providers/azurestack/r/virtual_machine_scale_set.html) in the _Terraform Provider Documentation_