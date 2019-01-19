# Terraform::Google::LoggingBillingAccountExclusion

Manages a billing account logging exclusion. For more information see
[the official documentation](https://cloud.google.com/logging/docs/) and
[Excluding Logs](https://cloud.google.com/logging/docs/exclusions).

Note that you must have the "Logs Configuration Writer" IAM role (`roles/logging.configWriter`)
granted to the credentials used with Terraform.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

## See Also

* [google_logging_billing_account_exclusion](https://www.terraform.io/docs/providers/google/r/logging_billing_account_exclusion.html) in the _Terraform Provider Documentation_