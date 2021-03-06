# Terraform::AWS::NetworkInterfaceAttachment

Attach an Elastic network interface (ENI) resource with EC2 instance.

## Properties

`InstanceId` - (Required) Instance ID to attach.

`NetworkInterfaceId` - (Required) ENI ID to attach.

`DeviceIndex` - (Required) Network interface index (int).


## Return Values

### Fn::GetAtt

`InstanceId` - Instance ID.

`NetworkInterfaceId` - Network interface ID.

`AttachmentId` - The ENI Attachment ID.

`Status` - The status of the Network Interface Attachment.

## See Also

* [aws_network_interface_attachment](https://www.terraform.io/docs/providers/aws/r/network_interface_attachment.html) in the _Terraform Provider Documentation_