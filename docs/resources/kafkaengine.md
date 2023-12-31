---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "clickhouse_kafkaengine Resource - terraform-provider-clickhouse"
subcategory: ""
description: |-
  Clickhouse KafkaEngine Table
---

# clickhouse_kafkaengine (Resource)

Clickhouse KafkaEngine Table

## Example Usage

```terraform
provider "clickhouse" {}

resource "clickhouse_database" "new_database" {
  name    = "new_db"
  comment = "new db test comment"
}

resource "clickhouse_kafkaengine" "new_table2" {
  name          = "test_kafka_engine"
  database_name = clickhouse_database.new_database.name
  columns = [{
    name = "a"
    type = "String"
    }, {
    name = "b"
    type = "String"
  }]
  kafka_broker_list               = "kafka:9092"
  kafka_topic_list                = "topic1"
  kafka_group_name                = "topic1.group"
  kafka_format                    = "AvroConfluent"
  format_avro_schema_registry_url = "http://schema-registry:8081"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `columns` (Attributes List) Clickhouse Table Column List (see [below for nested schema](#nestedatt--columns))
- `database_name` (String) Clickhouse Database Name
- `name` (String) Clickhouse Table Name

### Optional

- `cluster_name` (String) Clickhouse Cluster Name
- `format_avro_schema_registry_url` (String) Clickhouse Format Avro Schema Registry URL
- `kafka_broker_list` (String) Clickhouse Kafka Broker List
- `kafka_format` (String) Clickhouse Kafka Format
- `kafka_group_name` (String) Clickhouse Kafka Group Name
- `kafka_topic_list` (String) Clickhouse Kafka Topic List
- `named_collection_name` (String) Clickhouse Named Collection containing kafka config

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedatt--columns"></a>
### Nested Schema for `columns`

Required:

- `name` (String) Clickhouse Table Column name
- `type` (String) Clickhouse Table Column type
