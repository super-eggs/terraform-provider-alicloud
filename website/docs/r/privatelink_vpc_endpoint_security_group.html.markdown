---
subcategory: "Private Link"
layout: "alicloud"
page_title: "Alicloud: alicloud_privatelink_vpc_endpoint_security_group"
sidebar_current: "docs-alicloud-resource-privatelink-vpc-endpoint-security-group"
description: |-
  Provides a Alicloud Private Link Vpc Endpoint Security Group resource.
---

# alicloud\_privatelink\_vpc\_endpoint\_security\_group

Provides a Private Link Vpc Endpoint Security Group resource.

For information about Private Link Vpc Endpoint Security Group and how to use it, see [What is Vpc Endpoint Security Group](https://help.aliyun.com/).

-> **NOTE:** Available in v1.139.0+.

## Example Usage

Basic Usage

```terraform
resource "alicloud_privatelink_vpc_endpoint" "example" {
  security_group_ids = [example_value]
  vpc_endpoint_name  = "example_value"
  vpc_id             = "example_value"
}

resource "alicloud_privatelink_vpc_endpoint_security_group" "example" {
  endpoint_id       = alicloud_privatelink_vpc_endpoint.example.endpoint_id
  security_group_id = "example_value"
}

```

## Argument Reference

The following arguments are supported:

* `dry_run` - (Optional) The dry run.
* `endpoint_id` - (Required, ForceNew) EndpointId.
* `security_group_id` - (Required, ForceNew) SecurityGroupId.

## Attributes Reference

The following attributes are exported:

* `id` - The resource ID of Vpc Endpoint Security Group. The value formats as `<endpoint_id>:<security_group_id>`.

### Timeouts

The `timeouts` block allows you to specify [timeouts](https://www.terraform.io/docs/configuration-0-11/resources.html#timeouts) for certain actions:

* `create` - (Defaults to 4 mins) Used when create the Vpc Endpoint Security Group.
* `delete` - (Defaults to 4 mins) Used when delete the Vpc Endpoint Security Group.

## Import

Private Link Vpc Endpoint Security Group can be imported using the id, e.g.

```
$ terraform import alicloud_privatelink_vpc_endpoint_security_group.example <endpoint_id>:<security_group_id>
```