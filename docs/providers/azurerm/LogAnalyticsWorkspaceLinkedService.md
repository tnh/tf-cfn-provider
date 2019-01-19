# Terraform::AzureRM::LogAnalyticsWorkspaceLinkedService

Links a Log Analytics (formally Operational Insights) Workspace to another resource. The (currently) only linkable service is an Azure Automation Account.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Id` - The Log Analytics Linked Service ID.

`Name` - The automatically generated name of the Linked Service. This cannot be specified. The format is always `<workspace_name>/<linked_service_name>` e.g. `workspace1/Automation`.

## See Also

* [azurerm_log_analytics_workspace_linked_service](https://www.terraform.io/docs/providers/azurerm/r/log_analytics_workspace_linked_service.html) in the _Terraform Provider Documentation_