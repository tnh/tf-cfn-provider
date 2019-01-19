# Terraform::HuaweiCloud::CsbsBackupV1

Provides an HuaweiCloud Backup of Resources.

## Return Values

### Fn::GetAtt

Fn::GetAtt returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

`Status` -  Status of backup Volume.

`BackupRecordId` - Specifies backup record ID.

`SpaceSavingRatio` -  Specifies space saving rate.

`Name` - Name of backup data.

`Bootable` -  Specifies whether the disk is bootable.

`AverageSpeed` -  Specifies the average speed.

`SourceVolumeSize` -  Shows source volume size in GB.

`SourceVolumeId` -  It specifies source volume ID.

`Incremental` -  Shows whether incremental backup is used.

`SnapshotId` -  ID of snapshot.

`SourceVolumeName` -  Specifies source volume name.

`ImageType` - Specifies image type.

`Id` -  Specifies Cinder backup ID.

`Size` -  Specifies accumulated size (MB) of backups.

`Eip` - Specifies elastic IP address of the ECS.

`CloudServiceType` - Specifies ECS type.

`Ram` - Specifies memory size of the ECS, in MB.

`Vcpus` - Specifies CPU cores corresponding to the ECS.

`PrivateIp` - It specifies internal IP address of the ECS.

`Disk` - Shows system disk size corresponding to the ECS specifications.

## See Also

* [huaweicloud_csbs_backup_v1](https://www.terraform.io/docs/providers/huaweicloud/r/csbs_backup_v1.html) in the _Terraform Provider Documentation_