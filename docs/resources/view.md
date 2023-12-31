---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "clickhouse_view Resource - terraform-provider-clickhouse"
subcategory: ""
description: |-
  Clickhouse view
---

# clickhouse_view (Resource)

Clickhouse view

## Example Usage

```terraform
provider "clickhouse" {}

resource "clickhouse_database" "test" {
  name = "test"
}

resource "clickhouse_view" "new_view" {
  name          = "new_view"
  database_name = clickhouse_database.test.name
  sql           = <<EOT
SELECT
    event_time,
    type,
    query,
    initial_user
FROM system.query_log
ORDER BY event_time DESC
LIMIT 10
EOT
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `database_name` (String) Clickhouse database name
- `name` (String) Clickhouse database name
- `sql` (String) Clickhouse database comment

### Optional

- `cluster_name` (String) Clickhouse database name

### Read-Only

- `id` (String) The ID of this resource.
