# Terraform::Google::Project

Allows creation and management of a Google Cloud Platform project.

Projects created with this resource must be associated with an Organization.
See the [Organization documentation](https://cloud.google.com/resource-manager/docs/quickstarts) for more details.

The service account used to run Terraform when creating a `google_project`
resource must have `roles/resourcemanager.projectCreator`. See the
[Access Control for Organizations Using IAM](https://cloud.google.com/resource-manager/docs/access-control-org)
doc for more information.

Note that prior to 0.8.5, `google_project` functioned like a data source,
meaning any project referenced by it had to be created and managed outside
Terraform. As of 0.8.5, `google_project` functions like any other Terraform
resource, with Terraform creating and managing the project. To replicate the old
behavior, either:

* Use the project ID directly in whatever is referencing the project, using the
  [google_project_iam_policy](/docs/providers/google/r/google_project_iam.html)
  to replace the old `policy_data` property.
* Use the [import](/docs/import/usage.html) functionality
  to import your pre-existing project into Terraform, where it can be referenced and
  used just like always, keeping in mind that Terraform will attempt to undo any changes
  made outside Terraform.

~> It's important to note that any project resources that were added to your Terraform config
prior to 0.8.5 will continue to function as they always have, and will not be managed by
Terraform. Only newly added projects are affected.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Number` - The numeric identifier of the project.

## See Also

* [google_project](https://www.terraform.io/docs/providers/google/r/project.html) in the _Terraform Provider Documentation_