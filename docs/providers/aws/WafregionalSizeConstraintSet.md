# Terraform::AWS::WafregionalSizeConstraintSet

Provides a WAF Regional Size Constraint Set Resource for use with Application Load Balancer.

## Properties

`Name` - (Required) The name or description of the Size Constraint Set.

`SizeConstraints` - (Optional) Specifies the parts of web requests that you want to inspect the size of.


## Return Values

### Fn::GetAtt

`Id` - The ID of the WAF Size Constraint Set.

## See Also

* [aws_wafregional_size_constraint_set](https://www.terraform.io/docs/providers/aws/r/wafregional_size_constraint_set.html) in the _Terraform Provider Documentation_