---
layout: "oci"
page_title: "OCI: oci_file_storage_mount_targets"
sidebar_current: "docs-oci-datasource-file_storage-mount_targets"
description: |-
  Provides a list of MountTargets
---

# Data Source: oci_file_storage_mount_targets
The `oci_file_storage_mount_targets` data source allows access to the list of OCI mount_targets

Lists the mount target resources in the specified compartment.


## Example Usage

```hcl
data "oci_file_storage_mount_targets" "test_mount_targets" {
	#Required
	availability_domain = "${var.mount_target_availability_domain}"
	compartment_id = "${var.compartment_id}"

	#Optional
	display_name = "${var.mount_target_display_name}"
	export_set_id = "${oci_file_storage_export_set.test_export_set.id}"
	id = "${var.mount_target_id}"
	state = "${var.mount_target_state}"
}
```

## Argument Reference

The following arguments are supported:

* `availability_domain` - (Required) The name of the availability domain.  Example: `Uocm:PHX-AD-1` 
* `compartment_id` - (Required) The OCID of the compartment.
* `display_name` - (Optional) A user-friendly name. It does not have to be unique, and it is changeable.  Example: `My resource` 
* `export_set_id` - (Optional) The OCID of the export set.
* `id` - (Optional) Filter results by OCID. Must be an OCID of the correct type for the resouce type. 
* `state` - (Optional) Filter results by the specified lifecycle state. Must be a valid state for the resource type. 


## Attributes Reference

The following attributes are exported:

* `mount_targets` - The list of mount_targets.

### MountTarget Reference

The following attributes are exported:

* `availability_domain` - The availability domain the mount target is in. May be unset as a blank or NULL value.  Example: `Uocm:PHX-AD-1` 
* `compartment_id` - The OCID of the compartment that contains the mount target.
* `display_name` - A user-friendly name. It does not have to be unique, and it is changeable. Avoid entering confidential information.  Example: `My mount target` 
* `export_set_id` - The OCID of the associated export set. Controls what file systems will be exported through Network File System (NFS) protocol on this mount target. 
* `id` - The OCID of the mount target.
* `lifecycle_details` - Additional information about the current 'lifecycleState'.
* `private_ip_ids` - The OCIDs of the private IP addresses associated with this mount target.
* `state` - The current state of the mount target.
* `subnet_id` - The OCID of the subnet the mount target is in.
* `time_created` - The date and time the mount target was created, expressed in [RFC 3339](https://tools.ietf.org/rfc/rfc3339) timestamp format.  Example: `2016-08-25T21:10:29.600Z` 

