# Terraform::Brightbox::DatabaseServer

Provides a Brightbox Database Server resource. This can be used to create,
modify, and delete Database Servers.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Id` - The ID of the Database Server.

`AdminUsername` - The username used to log onto the database.

`AdminPassword` - The password used to log onto the database.

`Status` - Current state of the database server, usually `active` or `deleted`.

`Locked` - True if database server has been set to locked and cannot be deleted.

## See Also

* [brightbox_database_server](https://www.terraform.io/docs/providers/brightbox/r/database_server.html) in the _Terraform Provider Documentation_