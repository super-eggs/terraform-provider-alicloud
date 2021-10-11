---
subcategory: "Private Link"
layout: "alicloud"
page_title: "Alicloud: alicloud_privatelink_vpc_endpoint_security_groups"
sidebar_current: "docs-alicloud-datasource-privatelink-vpc-endpoint-security-groups"
description: |-
  Provides a list of Privatelink Vpc Endpoint Security Groups to the user.
---

# alicloud\_privatelink\_vpc\_endpoint\_security\_groups

This data source provides the Privatelink Vpc Endpoint Security Groups of the current Alibaba Cloud user.

-> **NOTE:** Available in v1.139.0+.

## Example Usage

Basic Usage

```terraform
data "alicloud_privatelink_vpc_endpoint_security_groups" "ids" {
  endpoint_id = "example_value"
  ids         = ["example_value-1", "example_value-2"]
}
output "privatelink_vpc_endpoint_security_group_id_1" {
  value = data.alicloud_privatelink_vpc_endpoint_security_groups.ids.groups.0.id
}
            
```

## Argument Reference

The following arguments are supported:

* `endpoint_id` - (Required, ForceNew) EndpointId.
* `ids` - (Optional, ForceNew, Computed)  A list of Vpc Endpoint Security Group IDs.
* `output_file` - (Optional) File name where to save data source results (after running `terraform plan`).

## Argument Reference

The following attributes are exported in addition to the arguments listed above:

* `groups` - A list of Privatelink Vpc Endpoint Security Groups. Each element contains the following attributes:
	* `endpoint_id` - EndpointId.
	* `id` - The ID of the Vpc Endpoint Security Group.
	* `security_group_id` - SecurityGroupId.