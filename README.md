This [dbt](https://github.com/dbt-labs/dbt) package contains macros that can be (re)used across dbt projects.

## Installation Instructions

Check [dbt Hub](https://hub.getdbt.com/dbt-labs/dbt_utils/latest/) for the latest installation instructions, or [read the docs](https://docs.getdbt.com/docs/package-management) for more information on installing packages.

----

<!--This table of contents is automatically generated. Any manual changes between the ts and te tags will be overridden!-->
<!--ts-->
   * [Installation Instructions](#installation-instructions)
   * [Generic Tests](#generic-tests)
      * [equal_rowcount (<a href="macros/generic_tests/equal_rowcount.sql">source</a>)](#equal_rowcount-source)
      * [fewer_rows_than (<a href="macros/generic_tests/fewer_rows_than.sql">source</a>)](#fewer_rows_than-source)
      * [equality (<a href="macros/generic_tests/equality.sql">source</a>)](#equality-source)
      * [expression_is_true (<a href="macros/generic_tests/expression_is_true.sql">source</a>)](#expression_is_true-source)
      * [recency (<a href="macros/generic_tests/recency.sql">source</a>)](#recency-source)
      * [at_least_one (<a href="macros/generic_tests/at_least_one.sql">source</a>)](#at_least_one-source)
      * [not_constant (<a href="macros/generic_tests/not_constant.sql">source</a>)](#not_constant-source)
      * [not_empty_string (<a href="macros/generic_tests/not_empty_string.sql">source</a>)](#not_empty_string-source)
      * [cardinality_equality (<a href="macros/generic_tests/cardinality_equality.sql">source</a>)](#cardinality_equality-source)
      * [not_null_proportion (<a href="macros/generic_tests/not_null_proportion.sql">source</a>)](#not_null_proportion-source)
      * [not_accepted_values (<a href="macros/generic_tests/not_accepted_values.sql">source</a>)](#not_accepted_values-source)
      * [relationships_where (<a href="macros/generic_tests/relationships_where.sql">source</a>)](#relationships_where-source)
      * [mutually_exclusive_ranges (<a href="macros/generic_tests/mutually_exclusive_ranges.sql">source</a>)](#mutually_exclusive_ranges-source)
      * [sequential_values (<a href="macros/generic_tests/sequential_values.sql">source</a>)](#sequential_values-source)
      * [unique_combination_of_columns (<a href="macros/generic_tests/unique_combination_of_columns.sql">source</a>)](#unique_combination_of_columns-source)
      * [accepted_range (<a href="macros/generic_tests/accepted_range.sql">source</a>)](#accepted_range-source)
      * [Grouping in tests](#grouping-in-tests)
   * [Macros](#macros)
   * [Introspective macros](#introspective-macros)
      * [get_column_values (<a href="macros/sql/get_column_values.sql">source</a>)](#get_column_values-source)
      * [get_filtered_columns_in_relation (<a href="macros/sql/get_filtered_columns_in_relation.sql">source</a>)](#get_filtered_columns_in_relation-source)
      * [get_relations_by_pattern (<a href="macros/sql/get_relations_by_pattern.sql">source</a>)](#get_relations_by_pattern-source)
      * [get_relations_by_prefix (<a href="macros/sql/get_relations_by_prefix.sql">source</a>)](#get_relations_by_prefix-source)
      * [get_query_results_as_dict (<a href="macros/sql/get_query_results_as_dict.sql">source</a>)](#get_query_results_as_dict-source)
      * [get_single_value (<a href="macros/sql/get_single_value.sql">source</a>)](#get_single_value-source)
   * [SQL generators](#sql-generators)
      * [date_spine (<a href="macros/sql/date_spine.sql">source</a>)](#date_spine-source)
      * [deduplicate (<a href="macros/sql/deduplicate.sql">source</a>)](#deduplicate-source)
      * [haversine_distance (<a href="macros/sql/haversine_distance.sql">source</a>)](#haversine_distance-source)
      * [group_by (<a href="macros/sql/groupby.sql">source</a>)](#group_by-source)
      * [star (<a href="macros/sql/star.sql">source</a>)](#star-source)
      * [union_relations (<a href="macros/sql/union.sql">source</a>)](#union_relations-source)
      * [generate_series (<a href="macros/sql/generate_series.sql">source</a>)](#generate_series-source)
      * [generate_surrogate_key (<a href="macros/sql/generate_surrogate_key.sql">source</a>)](#generate_surrogate_key-source)
      * [safe_add (<a href="macros/sql/safe_add.sql">source</a>)](#safe_add-source)
      * [safe_divide (<a href="macros/sql/safe_divide.sql">source</a>)](#safe_divide-source)
      * [safe_subtract (<a href="macros/sql/safe_subtract.sql">source</a>)](#safe_subtract-source)
      * [pivot (<a href="macros/sql/pivot.sql">source</a>)](#pivot-source)
      * [unpivot (<a href="macros/sql/unpivot.sql">source</a>)](#unpivot-source)
      * [width_bucket (<a href="macros/sql/width_bucket.sql">source</a>)](#width_bucket-source)
   * [Web macros](#web-macros)
      * [get_url_parameter (<a href="macros/web/get_url_parameter.sql">source</a>)](#get_url_parameter-source)
      * [get_url_host (<a href="macros/web/get_url_host.sql">source</a>)](#get_url_host-source)
      * [get_url_path (<a href="macros/web/get_url_path.sql">source</a>)](#get_url_path-source)
   * [Cross-database macros](#cross-database-macros)
   * [Jinja Helpers](#jinja-helpers)
      * [pretty_time (<a href="macros/jinja_helpers/pretty_time.sql">source</a>)](#pretty_time-source)
      * [pretty_log_format (<a href="macros/jinja_helpers/pretty_log_format.sql">source</a>)](#pretty_log_format-source)
      * [log_info (<a href="macros/jinja_helpers/log_info.sql">source</a>)](#log_info-source)
      * [slugify (<a href="macros/jinja_helpers/slugify.sql">source</a>)](#slugify-source)
   * [Materializations](#materializations)
      * [insert_by_period](#insert_by_period)
   * [Reporting bugs and contributing code](#reporting-bugs-and-contributing-code)
   * [Dispatch macros](#dispatch-macros)
   * [Getting started with dbt](#getting-started-with-dbt)
   * [Code of Conduct](#code-of-conduct)

<!-- Created by https://github.com/ekalinin/github-markdown-toc -->
<!-- Added by: runner, at: Thu Feb  9 00:20:43 UTC 2023 -->

<!--te-->
----

## Generic Tests

### equal_rowcount ([source](macros/generic_tests/equal_rowcount.sql))

Asserts that two relations have the same number of rows.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    tests:
      - dbt_utils.equal_rowcount:
          compare_model: ref('other_table_name')

```

This test supports the `group_by_columns` parameter; see [Grouping in tests](#grouping-in-tests) for details.

### fewer_rows_than ([source](macros/generic_tests/fewer_rows_than.sql))

Asserts that the respective model has fewer rows than the model being compared.

Usage:

```yaml
version: 2

models:
  - name: model_name
    tests:
      - dbt_utils.fewer_rows_than:
          compare_model: ref('other_table_name')
```

This test supports the `group_by_columns` parameter; see [Grouping in tests](#grouping-in-tests) for details.

### equality ([source](macros/generic_tests/equality.sql))

Asserts the equality of two relations. Optionally specify a subset of columns to compare or exclude, and a precision to compare numeric columns on.

**Usage:**

```yaml
version: 2

models:
  # compare the entire table 
  - name: model_name
    tests:
      - dbt_utils.equality:
          compare_model: ref('other_table_name')

  # only compare some of the columns
  - name: model_name_compare_columns
    tests:
      - dbt_utils.equality:
          compare_model: ref('other_table_name')
          compare_columns:
            - first_column
            - second_column
          precision: 4

  # compare all columns except the ones on the ignore list
  - name: model_name_exclude_columns
    tests:
      - dbt_utils.equality:
          compare_model: ref('other_table_name')
          exclude_columns:
            - third_column
```

### expression_is_true ([source](macros/generic_tests/expression_is_true.sql))

Asserts that a valid SQL expression is true for all records. This is useful when checking integrity across columns.
Examples:

- Verify an outcome based on the application of basic algebraic operations between columns.
- Verify the length of a column.
- Verify the truth value of a column.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    tests:
      - dbt_utils.expression_is_true:
          expression: "col_a + col_b = total"
```

The macro accepts an optional argument `where` that allows for asserting
the `expression` on a subset of all records.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    tests:
      - dbt_utils.expression_is_true:
          expression: "col_a + col_b = total"
          config:
            where: "created_at > '2018-12-31'"
```

```yaml
version: 2
models:
  - name: model_name
    columns:
      - name: col_a
        tests:
          - dbt_utils.expression_is_true:
              expression: '>= 1'
      - name: col_b
        tests:
          - dbt_utils.expression_is_true:
              expression: '= 1'
              config:
                where: col_a = 1
```

### recency ([source](macros/generic_tests/recency.sql))

Asserts that a timestamp column in the reference model contains data that is at least as recent as the defined date interval.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    tests:
      - dbt_utils.recency:
          datepart: day
          field: created_at
          interval: 1
```
This test supports the `group_by_columns` parameter; see [Grouping in tests](#grouping-in-tests) for details.

### at_least_one ([source](macros/generic_tests/at_least_one.sql))

Asserts that a column has at least one value that is not `null`.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    columns:
      - name: col_name
        tests:
          - dbt_utils.at_least_one
```

This test supports the `group_by_columns` parameter; see [Grouping in tests](#grouping-in-tests) for details.

### not_constant ([source](macros/generic_tests/not_constant.sql))

Asserts that a column does not have the same value in all rows.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    columns:
      - name: column_name
        tests:
          - dbt_utils.not_constant
```

This test supports the `group_by_columns` parameter; see [Grouping in tests](#grouping-in-tests) for details.

### not_empty_string ([source](macros/generic_tests/not_empty_string.sql))
Asserts that a column does not have any values equal to `''`. 

**Usage:**
```yaml
version: 2

models:
  - name: model_name
    columns:
      - name: column_name
        tests:
          - dbt_utils.not_empty_string
```

The macro accepts an optional argument `trim_whitespace` that controls whether whitespace should be trimmed from the column when evaluating. The default is `true`. 

**Usage:**
```yaml
version: 2

models:
  - name: model_name
    columns:
      - name: column_name
        tests:
          - dbt_utils.not_empty_string:
              trim_whitespace: false
              
```

### cardinality_equality ([source](macros/generic_tests/cardinality_equality.sql))

Asserts that values in a given column have exactly the same cardinality as values from a different column in a different model.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    columns:
      - name: from_column
        tests:
          - dbt_utils.cardinality_equality:
              field: other_column_name
              to: ref('other_model_name')
```


### not_null_proportion ([source](macros/generic_tests/not_null_proportion.sql))

Asserts that the proportion of non-null values present in a column is between a specified range [`at_least`, `at_most`] where `at_most` is an optional argument (default: `1.0`).

**Usage:**

```yaml
version: 2

models:
  - name: my_model
    columns:
      - name: id
        tests:
          - dbt_utils.not_null_proportion:
              at_least: 0.95
```

This test supports the `group_by_columns` parameter; see [Grouping in tests](#grouping-in-tests) for details.

### not_accepted_values ([source](macros/generic_tests/not_accepted_values.sql))

Asserts that there are no rows that match the given values.

Usage:

```yaml
version: 2

models:
  - name: my_model
    columns:
      - name: city
        tests:
          - dbt_utils.not_accepted_values:
              values: ['Barcelona', 'New York']
```

### relationships_where ([source](macros/generic_tests/relationships_where.sql))

Asserts the referential integrity between two relations (same as the core relationships assertions) with an added predicate to filter out some rows from the test. This is useful to exclude records such as test entities, rows created in the last X minutes/hours to account for temporary gaps due to ETL limitations, etc.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    columns:
      - name: id
        tests:
          - dbt_utils.relationships_where:
              to: ref('other_model_name')
              field: client_id
              from_condition: id <> '4ca448b8-24bf-4b88-96c6-b1609499c38b'
              to_condition: created_date >= '2020-01-01'
```

### mutually_exclusive_ranges ([source](macros/generic_tests/mutually_exclusive_ranges.sql))

Asserts that for a given lower_bound_column and upper_bound_column,
the ranges between the lower and upper bounds do not overlap with the ranges
of another row.

**Usage:**

```yaml
version: 2

models:
  # test that age ranges do not overlap
  - name: age_brackets
    tests:
      - dbt_utils.mutually_exclusive_ranges:
          lower_bound_column: min_age
          upper_bound_column: max_age
          gaps: not_allowed

  # test that each customer can only have one subscription at a time
  - name: subscriptions
    tests:
      - dbt_utils.mutually_exclusive_ranges:
          lower_bound_column: started_at
          upper_bound_column: ended_at
          partition_by: customer_id
          gaps: required

  # test that each customer can have subscriptions that start and end on the same date
  - name: subscriptions
    tests:
      - dbt_utils.mutually_exclusive_ranges:
          lower_bound_column: started_at
          upper_bound_column: ended_at
          partition_by: customer_id
          zero_length_range_allowed: true
```

**Args:**

- `lower_bound_column` (required): The name of the column that represents the
lower value of the range. Must be not null.
- `upper_bound_column` (required): The name of the column that represents the
upper value of the range. Must be not null.
- `partition_by` (optional): If a subset of records should be mutually exclusive
(e.g. all periods for a single subscription_id are mutually exclusive), use this
argument to indicate which column to partition by. `default=none`
- `gaps` (optional): Whether there can be gaps are allowed between ranges.
`default='allowed', one_of=['not_allowed', 'allowed', 'required']`
- `zero_length_range_allowed` (optional): Whether ranges can start and end on the same date.
`default=False`

**Note:** Both `lower_bound_column` and `upper_bound_column` should be not null.
If this is not the case in your data source, consider passing a coalesce function
to the `lower_` and `upper_bound_column` arguments, like so:

```yaml
version: 2

models:
  - name: subscriptions
    tests:
      - dbt_utils.mutually_exclusive_ranges:
          lower_bound_column: coalesce(started_at, '1900-01-01')
          upper_bound_column: coalesce(ended_at, '2099-12-31')
          partition_by: customer_id
          gaps: allowed
```

<details>
<summary>Additional `gaps` and `zero_length_range_allowed` examples</summary>
  **Understanding the `gaps` argument:**

  Here are a number of examples for each allowed `gaps` argument.

- `gaps: not_allowed`: The upper bound of one record must be the lower bound of
  the next record.

  | lower_bound | upper_bound |
  |-------------|-------------|
  | 0           | 1           |
  | 1           | 2           |
  | 2           | 3           |

- `gaps: allowed` (default): There may be a gap between the upper bound of one
  record and the lower bound of the next record.

  | lower_bound | upper_bound |
  |-------------|-------------|
  | 0           | 1           |
  | 2           | 3           |
  | 3           | 4           |

- `gaps: required`: There must be a gap between the upper bound of one record and
  the lower bound of the next record (common for date ranges).

  | lower_bound | upper_bound |
  |-------------|-------------|
  | 0           | 1           |
  | 2           | 3           |
  | 4           | 5           |

  **Understanding the `zero_length_range_allowed` argument:**
  Here are a number of examples for each allowed `zero_length_range_allowed` argument.

- `zero_length_range_allowed: false`: (default) The upper bound of each record must be greater than its lower bound.

  | lower_bound | upper_bound |
  |-------------|-------------|
  | 0           | 1           |
  | 1           | 2           |
  | 2           | 3           |

- `zero_length_range_allowed: true`: The upper bound of each record can be greater than or equal to its lower bound.

  | lower_bound | upper_bound |
  |-------------|-------------|
  | 0           | 1           |
  | 2           | 2           |
  | 3           | 4           |

</details>

### sequential_values ([source](macros/generic_tests/sequential_values.sql))

This test confirms that a column contains sequential values. It can be used
for both numeric values, and datetime values, as follows:

```yaml
version: 2

seeds:
  - name: util_even_numbers
    columns:
      - name: i
        tests:
          - dbt_utils.sequential_values:
              interval: 2


  - name: util_hours
    columns:
      - name: date_hour
        tests:
          - dbt_utils.sequential_values:
              interval: 1
              datepart: 'hour'
```

**Args:**

- `interval` (default=1): The gap between two sequential values
- `datepart` (default=None): Used when the gaps are a unit of time. If omitted, the test will check for a numeric gap.

This test supports the `group_by_columns` parameter; see [Grouping in tests](#grouping-in-tests) for details.

### unique_combination_of_columns ([source](macros/generic_tests/unique_combination_of_columns.sql))

Asserts that the combination of columns is unique. For example, the
combination of month and product is unique, however neither column is unique
in isolation.

We generally recommend testing this uniqueness condition by either:

- generating a [surrogate_key](#generate_surrogate_key-source) for your model and testing
the uniqueness of said key, OR
- passing the `unique` test a concatenation of the columns:
    ```yaml
    models:
      - name: revenue_by_product_by_month
        tests:
          - unique:
              column_name: "month || '-' || product"
    ```

However, these approaches can become non-perfomant on large data sets, in which
case we recommend using this test instead.

**Usage:**

```yaml
- name: revenue_by_product_by_month
  tests:
    - dbt_utils.unique_combination_of_columns:
        combination_of_columns:
          - month
          - product
```

An optional `quote_columns` argument (`default=false`) can also be used if a column name needs to be quoted.

```yaml
- name: revenue_by_product_by_month
  tests:
    - dbt_utils.unique_combination_of_columns:
        combination_of_columns:
          - month
          - group
        quote_columns: true

```

### accepted_range ([source](macros/generic_tests/accepted_range.sql))

Asserts that a column's values fall inside an expected range. Any combination of `min_value` and `max_value` is allowed, and the range can be inclusive or exclusive. Provide [a `where` argument](https://docs.getdbt.com/reference/resource-configs/where) to filter to specific records only.

In addition to comparisons to a scalar value, you can also compare to another column's values. Any data type that supports the `>` or `<` operators can be compared, so you could also run tests like checking that all order dates are in the past.

**Usage:**

```yaml
version: 2

models:
  - name: model_name
    columns:
      - name: user_id
        tests:
          - dbt_utils.accepted_range:
              min_value: 0
              inclusive: false

      - name: account_created_at
        tests:
          - dbt_utils.accepted_range:
              max_value: "getdate()"
              #inclusive is true by default

      - name: num_returned_orders
        tests:
          - dbt_utils.accepted_range:
              min_value: 0
              max_value: "num_orders"

      - name: num_web_sessions
        tests:
          - dbt_utils.accepted_range:
              min_value: 0
              inclusive: false
              config:
                where: "num_orders > 0"
```

----

### Grouping in tests

Certain tests support the optional `group_by_columns` argument to provide more granularity in performing tests. This can be useful when:

- Some data checks can only be expressed within a group (e.g. ID values should be unique within a group but can be repeated between groups)
- Some data checks are more precise when done by group (e.g. not only should table rowcounts be equal but the counts within each group should be equal)

This feature is currently available for the following data tests:

- [equal_rowcount](#equal_rowcount-source)
- [fewer_rows_than](#fewer_rows_than-source)
- [recency](#recency-source)
- [at_least_one](#at_least_one-source)
- [not_constant](#not_constant-source)
- [sequential_values](#sequential_values-source)
- [not_null_proportion](#not_null_proportion-source)

To use this feature, the names of grouping variables can be passed as a list. For example, to test for at least one valid value by group, the `group_by_columns` argument could be used as follows:

```yaml
  - name: data_test_at_least_one
    columns:
      - name: field
        tests:
          - dbt_utils.at_least_one:
              group_by_columns: ['customer_segment']
```

## Macros

## Introspective macros

These macros run a query and return the results of the query as objects. They are typically abstractions over the [statement blocks](https://docs.getdbt.com/reference/dbt-jinja-functions/statement-blocks) in dbt.

### get_column_values ([source](macros/sql/get_column_values.sql))

This macro returns the unique values for a column in a given [relation](https://docs.getdbt.com/docs/writing-code-in-dbt/class-reference/#relation) as an array.

**Args:**

- `table` (required): a [Relation](https://docs.getdbt.com/reference/dbt-classes#relation) (a `ref` or `source`) that contains the list of columns you wish to select from
- `column` (required): The name of the column you wish to find the column values of
- `where` (optional, default=`none`): A where clause to filter the column values by.
- `order_by` (optional, default=`'count(*) desc'`): How the results should be ordered. Must be an aggregate function, i.e. count(*), max(sort_order). The default is to order by `count(*) desc`, i.e. decreasing frequency. Setting this as `'my_column'` will sort alphabetically, while `'min(created_at)'` will sort by when the value was first observed.
- `max_records` (optional, default=`none`): The maximum number of column values you want to return
- `default` (optional, default=`[]`): The results this macro should return if the relation has not yet been created (and therefore has no column values).

**Usage:**

```sql
-- Returns a list of the payment_methods in the stg_payments model_
{% set payment_methods = dbt_utils.get_column_values(table=ref('stg_payments'), column='payment_method') %}

{% for payment_method in payment_methods %}
    ...
{% endfor %}

...
```

```sql
-- Returns the list sorted alphabetically
{% set payment_methods = dbt_utils.get_column_values(
        table=ref('stg_payments'),
        where="payment_method = 'bank_transfer'",
        column='payment_method',
        order_by='payment_method'
) %}
```

```sql
-- Returns the list sorted my most recently observed
{% set payment_methods = dbt_utils.get_column_values(
        table=ref('stg_payments'),
        column='payment_method',
        order_by='max(created_at) desc',
        max_records=50,
        default=['bank_transfer', 'coupon', 'credit_card']
%}
...
```

### get_filtered_columns_in_relation ([source](macros/sql/get_filtered_columns_in_relation.sql))

This macro returns an iterable Jinja list of columns for a given [relation](https://docs.getdbt.com/docs/writing-code-in-dbt/class-reference/#relation), (i.e. not from a CTE)

- optionally exclude columns
- the input values are not case-sensitive (input uppercase or lowercase and it will work!)

> Note: The native [`adapter.get_columns_in_relation` macro](https://docs.getdbt.com/reference/dbt-jinja-functions/adapter#get_columns_in_relation) allows you
to pull column names in a non-filtered fashion, also bringing along with it other (potentially unwanted) information, such as dtype, char_size, numeric_precision, etc.

**Args:**

- `from` (required): a [Relation](https://docs.getdbt.com/reference/dbt-classes#relation) (a `ref` or `source`) that contains the list of columns you wish to select from
- `except` (optional, default=`[]`): The name of the columns you wish to exclude. (case-insensitive)

**Usage:**

```sql
-- Returns a list of the columns from a relation, so you can then iterate in a for loop
{% set column_names = dbt_utils.get_filtered_columns_in_relation(from=ref('your_model'), except=["field_1", "field_2"]) %}
...
{% for column_name in column_names %}
    max({{ column_name }}) ... as max_'{{ column_name }}',
{% endfor %}
...
```

### get_relations_by_pattern ([source](macros/sql/get_relations_by_pattern.sql))

Returns a list of [Relations](https://docs.getdbt.com/docs/writing-code-in-dbt/class-reference/#relation)
that match a given schema- or table-name pattern.

This macro is particularly handy when paired with `union_relations`.

**Usage:**

```sql
-- Returns a list of relations that match schema_pattern%.table
{% set relations = dbt_utils.get_relations_by_pattern('schema_pattern%', 'table_pattern') %}

-- Returns a list of relations that match schema_pattern.table_pattern%
{% set relations = dbt_utils.get_relations_by_pattern('schema_pattern', 'table_pattern%') %}

-- Returns a list of relations as above, excluding any that end in `deprecated`
{% set relations = dbt_utils.get_relations_by_pattern('schema_pattern', 'table_pattern%', '%deprecated') %}

-- Example using the union_relations macro
{% set event_relations = dbt_utils.get_relations_by_pattern('venue%', 'clicks') %}
{{ dbt_utils.union_relations(relations = event_relations) }}
```

**Args:**

- `schema_pattern` (required): The schema pattern to inspect for relations.
- `table_pattern` (required): The name of the table/view (case insensitive).
- `exclude` (optional): Exclude any relations that match this table pattern.
- `database` (optional, default = `target.database`): The database to inspect
for relations.

**Examples:**
Generate drop statements for all Relations that match a naming pattern:

```sql
{% set relations_to_drop = dbt_utils.get_relations_by_pattern(
    schema_pattern='public',
    table_pattern='dbt\_%'
) %}

{% set sql_to_execute = [] %}

{{ log('Statements to run:', info=True) }}

{% for relation in relations_to_drop %}
    {% set drop_command -%}
    -- drop {{ relation.type }} {{ relation }} cascade;
    {%- endset %}
    {% do log(drop_command, info=True) %}
    {% do sql_to_execute.append(drop_command) %}
{% endfor %}
```

### get_relations_by_prefix ([source](macros/sql/get_relations_by_prefix.sql))

> This macro will soon be deprecated in favor of the more flexible `get_relations_by_pattern` macro (above)

Returns a list of [Relations](https://docs.getdbt.com/docs/writing-code-in-dbt/class-reference/#relation)
that match a given prefix, with an optional exclusion pattern. It's particularly
handy paired with `union_relations`.

**Usage:**

```sql
-- Returns a list of relations that match schema.prefix%
{% set relations = dbt_utils.get_relations_by_prefix('my_schema', 'my_prefix') %}

-- Returns a list of relations as above, excluding any that end in `deprecated`
{% set relations = dbt_utils.get_relations_by_prefix('my_schema', 'my_prefix', '%deprecated') %}

-- Example using the union_relations macro
{% set event_relations = dbt_utils.get_relations_by_prefix('events', 'event_') %}
{{ dbt_utils.union_relations(relations = event_relations) }}
```

**Args:**

- `schema` (required): The schema to inspect for relations.
- `prefix` (required): The prefix of the table/view (case insensitive)
- `exclude` (optional): Exclude any relations that match this pattern.
- `database` (optional, default = `target.database`): The database to inspect
for relations.

### get_query_results_as_dict ([source](macros/sql/get_query_results_as_dict.sql))

This macro returns a dictionary from a sql query, so that you don't need to interact with the Agate library to operate on the result

**Usage:**

```sql
{% set sql_statement %}
    select city, state from {{ ref('users') }}
{% endset %}

{%- set places = dbt_utils.get_query_results_as_dict(sql_statement) -%}

select

    {% for city in places['CITY'] | unique -%}
      sum(case when city = '{{ city }}' then 1 else 0 end) as users_in_{{ dbt_utils.slugify(city) }},
    {% endfor %}

    {% for state in places['STATE'] | unique -%}
      sum(case when state = '{{ state }}' then 1 else 0 end) as users_in_{{ state }},
    {% endfor %}

    count(*) as total_total

from {{ ref('users') }}
```

### get_single_value ([source](macros/sql/get_single_value.sql))

This macro returns a single value from a sql query, so that you don't need to interact with the Agate library to operate on the result

**Usage:**

```sql
{% set sql_statement %}
    select max(created_at) from {{ ref('processed_orders') }}
{% endset %}

{%- set newest_processed_order = dbt_utils.get_single_value(sql_statement, default="'2020-01-01'") -%}

select

    *,
    last_order_at > '{{ newest_processed_order }}' as has_unprocessed_order

from {{ ref('users') }}
```

## SQL generators

These macros generate SQL (either a complete query, or a part of a query). They often implement patterns that should be easy in SQL, but for some reason are much harder than they need to be.

### date_spine ([source](macros/sql/date_spine.sql))

This macro returns the sql required to build a date spine. The spine will include the `start_date` (if it is aligned to the `datepart`), but it will not include the `end_date`.

**Usage:**

```sql
{{ dbt_utils.date_spine(
    datepart="day",
    start_date="cast('2019-01-01' as date)",
    end_date="cast('2020-01-01' as date)"
   )
}}
```

### deduplicate ([source](macros/sql/deduplicate.sql))

This macro returns the sql required to remove duplicate rows from a model, source, or CTE.

**Args:**

- `relation` (required): a [Relation](https://docs.getdbt.com/reference/dbt-classes#relation) (a `ref` or `source`) or string which identifies the model to deduplicate.
- `partition_by` (required): column names (or expressions) to use to identify a set/window of rows out of which to select one as the deduplicated row.
- `order_by` (required): column names (or expressions) that determine the priority order of which row should be chosen if there are duplicates (comma-separated string). *NB.* if this order by clause results in ties then which row is returned may be nondeterministic across runs.

**Usage:**

```sql
{{ dbt_utils.deduplicate(
    relation=source('my_source', 'my_table'),
    partition_by='user_id, cast(timestamp as day)',
    order_by="timestamp desc",
   )
}}
```

```sql
{{ dbt_utils.deduplicate(
    relation=ref('my_model'),
    partition_by='user_id',
    order_by='effective_date desc, effective_sequence desc',
   )
}}
```

```sql
with my_cte as (
    select *
    from {{ source('my_source', 'my_table') }}
    where user_id = 1
),
deduplicated_cte as (
  {{ dbt_utils.deduplicate(
      relation='my_cte',
      partition_by='user_id, cast(timestamp as date)',
      order_by='timestamp desc',
     )
  }}
)
select * from deduplicated_cte
```

### haversine_distance ([source](macros/sql/haversine_distance.sql))

This macro calculates the [haversine distance](https://en.wikipedia.org/wiki/Haversine_formula) between a pair of x/y coordinates.

Optionally takes a `unit` string argument ('km' or 'mi') which defaults to miles (imperial system).

**Usage:**

```sql
{{ dbt_utils.haversine_distance(48.864716, 2.349014, 52.379189, 4.899431) }}

{{ dbt_utils.haversine_distance(
    lat1=48.864716,
    lon1=2.349014,
    lat2=52.379189,
    lon2=4.899431,
    unit='km'
) }}
```

**Args:**

- `lat1` (required): latitude of first location
- `lon1` (required): longitude of first location
- `lat2` (required): latitude of second location
- `lon3` (required): longitude of second location
- `unit` (optional, default=`'mi'`): one of `mi` (miles) or `km` (kilometers)

### group_by ([source](macros/sql/groupby.sql))

This macro builds a group by statement for fields 1...N

**Usage:**

```sql
{{ dbt_utils.group_by(n=3) }}
```

Would compile to:

```sql
group by 1,2,3
```

### star ([source](macros/sql/star.sql))

This macro generates a comma-separated list of all fields that exist in the `from` relation, excluding any fields
listed in the `except` argument. The construction is identical to `select * from {{ref('my_model')}}`, replacing star (`*`) with
the star macro.
This macro also has an optional `relation_alias` argument that will prefix all generated fields with an alias (`relation_alias`.`field_name`).
The macro also has optional `prefix` and `suffix` arguments. When one or both are provided, they will be concatenated onto each field's alias
in the output (`prefix` ~ `field_name` ~ `suffix`). NB: This prevents the output from being used in any context other than a select statement.
This macro also has an optional `quote_identifiers` argument that will encase the selected columns and their aliases in double quotes.

**Args:**

- `from` (required): a [Relation](https://docs.getdbt.com/reference/dbt-classes#relation) (a `ref` or `source`) that contains the list of columns you wish to select from
- `except` (optional, default=`[]`): The name of the columns you wish to exclude. (case-insensitive)
- `relation_alias` (optional, default=`''`): will prefix all generated fields with an alias (`relation_alias`.`field_name`).
- `prefix` (optional, default=`''`): will prefix the output `field_name` (`field_name as prefix_field_name`).
- `suffix` (optional, default=`''`): will suffix the output `field_name` (`field_name as field_name_suffix`).
- `quote_identifiers` (optional, default=`True`): will encase selected columns and aliases in double quotes (`"field_name" as "field_name"`).

**Usage:**

```sql
select
  {{ dbt_utils.star(ref('my_model')) }}
from {{ ref('my_model') }}

```

```sql
select
  {{ dbt_utils.star(from=ref('my_model'), quote_identifiers=False) }}
from {{ ref('my_model') }}

```

```sql
select
{{ dbt_utils.star(from=ref('my_model'), except=["exclude_field_1", "exclude_field_2"]) }}
from {{ ref('my_model') }}

```

```sql
select
{{ dbt_utils.star(from=ref('my_model'), except=["exclude_field_1", "exclude_field_2"], prefix="max_") }}
from {{ ref('my_model') }}

```

### union_relations ([source](macros/sql/union.sql))

This macro combines via `union all` an array of [Relations](https://docs.getdbt.com/docs/writing-code-in-dbt/class-reference/#relation),
even when columns have differing orders in each Relation, and/or some columns are
missing from some relations. Any columns exclusive to a subset of these
relations will be filled with `null` where not present. A new column
(`_dbt_source_relation`) is also added to indicate the source for each record.

**Usage:**

```sql
{{ dbt_utils.union_relations(
    relations=[ref('my_model'), source('my_source', 'my_table')],
    exclude=["_loaded_at"]
) }}
```

**Args:**

- `relations` (required): An array of [Relations](https://docs.getdbt.com/docs/writing-code-in-dbt/class-reference/#relation).
- `exclude` (optional): A list of column names that should be excluded from
the final query.
- `include` (optional): A list of column names that should be included in the
final query. Note the `include` and `exclude` arguments are mutually exclusive.
- `column_override` (optional): A dictionary of explicit column type overrides,
e.g. `{"some_field": "varchar(100)"}`.``
- `source_column_name` (optional, `default="_dbt_source_relation"`): The name of
the column that records the source of this row. Pass `None` to omit this column from the results.
- `where` (optional): Filter conditions to include in the `where` clause.

### generate_series ([source](macros/sql/generate_series.sql))

This macro implements a cross-database mechanism to generate an arbitrarily long list of numbers. Specify the maximum number you'd like in your list and it will create a 1-indexed SQL result set.

**Usage:**

```sql
{{ dbt_utils.generate_series(upper_bound=1000) }}
```

### generate_surrogate_key ([source](macros/sql/generate_surrogate_key.sql))

This macro implements a cross-database way to generate a hashed surrogate key using the fields specified.

**Usage:**

```sql
{{ dbt_utils.generate_surrogate_key(['field_a', 'field_b'[,...]]) }}
```

A precursor to this macro, `surrogate_key()`, treated nulls and blanks strings the same. If you need to enable this incorrect behaviour for backward compatibility reasons, add the following variable to your `dbt_project.yml`: 

```yaml
#dbt_project.yml
vars:
  surrogate_key_treat_nulls_as_empty_strings: true #turn on legacy behaviour
```

### safe_add ([source](macros/sql/safe_add.sql))

This macro implements a cross-database way to sum nullable fields using the fields specified.

**Usage:**

```sql
{{ dbt_utils.safe_add(['field_a', 'field_b', ...]) }}
```

### safe_divide ([source](macros/sql/safe_divide.sql))

This macro performs division but returns null if the denominator is 0. 

**Args:**

- `numerator` (required): The number or SQL expression you want to divide.
- `denominator` (required): The number or SQL expression you want to divide by.

**Usage:**

```sql
{{ dbt_utils.safe_divide('numerator', 'denominator') }}
```

### safe_subtract ([source](macros/sql/safe_subtract.sql))

This macro implements a cross-database way to take the difference of nullable fields using the fields specified.

**Usage:**

```sql
{{ dbt_utils.safe_subtract(['field_a', 'field_b', ...]) }}
```

### pivot ([source](macros/sql/pivot.sql))

This macro pivots values from rows to columns.

**Usage:**

```sql
{{ dbt_utils.pivot(<column>, <list of values>) }}
```

**Examples:**

    Input: orders

    | size | color |
    |------|-------|
    | S    | red   |
    | S    | blue  |
    | S    | red   |
    | M    | red   |

    select
      size,
      {{ dbt_utils.pivot(
          'color',
          dbt_utils.get_column_values(ref('orders'), 'color')
      ) }}
    from {{ ref('orders') }}
    group by size

    Output:

    | size | red | blue |
    |------|-----|------|
    | S    | 2   | 1    |
    | M    | 1   | 0    |

    Input: orders

    | size | color | quantity |
    |------|-------|----------|
    | S    | red   | 1        |
    | S    | blue  | 2        |
    | S    | red   | 4        |
    | M    | red   | 8        |

    select
      size,
      {{ dbt_utils.pivot(
          'color',
          dbt_utils.get_column_values(ref('orders'), 'color'),
          agg='sum',
          then_value='quantity',
          prefix='pre_',
          suffix='_post'
      ) }}
    from {{ ref('orders') }}
    group by size

    Output:

    | size | pre_red_post | pre_blue_post |
    |------|--------------|---------------|
    | S    | 5            | 2             |
    | M    | 8            | 0             |


**Args:**

- `column`: Column name, required
- `values`: List of row values to turn into columns, required
- `alias`: Whether to create column aliases, default is True
- `agg`: SQL aggregation function, default is sum
- `cmp`: SQL value comparison, default is =
- `prefix`: Column alias prefix, default is blank
- `suffix`: Column alias postfix, default is blank
- `then_value`: Value to use if comparison succeeds, default is 1
- `else_value`: Value to use if comparison fails, default is 0
- `quote_identifiers`: Whether to surround column aliases with double quotes, default is true

### unpivot ([source](macros/sql/unpivot.sql))

This macro "un-pivots" a table from wide format to long format. Functionality is similar to pandas [melt](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.melt.html) function.
Boolean values are replaced with the strings 'true'|'false'

**Usage:**

```sql
{{ dbt_utils.unpivot(
  relation=ref('table_name'),
  cast_to='datatype',
  exclude=[<list of columns to exclude from unpivot>],
  remove=[<list of columns to remove>],
  field_name=<column name for field>,
  value_name=<column name for value>
) }}
```

**Usage:**

    Input: orders

    | date       | size | color | status     |
    |------------|------|-------|------------|
    | 2017-01-01 | S    | red   | complete   |
    | 2017-03-01 | S    | red   | processing |

    {{ dbt_utils.unpivot(ref('orders'), cast_to='varchar', exclude=['date','status']) }}

    Output:

    | date       | status     | field_name | value |
    |------------|------------|------------|-------|
    | 2017-01-01 | complete   | size       | S     |
    | 2017-01-01 | complete   | color      | red   |
    | 2017-03-01 | processing | size       | S     |
    | 2017-03-01 | processing | color      | red   |

**Args:**

- `relation`: The [Relation](https://docs.getdbt.com/docs/writing-code-in-dbt/class-reference/#relation) to unpivot.
- `cast_to`: The data type to cast the unpivoted values to, default is varchar
- `exclude`: A list of columns to exclude from the unpivot operation but keep in the resulting table.
- `remove`: A list of columns to remove from the resulting table.
- `field_name`: column name in the resulting table for field
- `value_name`: column name in the resulting table for value
- `quote_identifiers` (optional, default=`False`): will encase selected columns and aliases in quotes according to your adapter's implementation of `adapter.quote` (e.g. `"field_name" as "field_name"`).

### width_bucket ([source](macros/sql/width_bucket.sql))

This macro is modeled after the `width_bucket` function natively available in Snowflake.

From the original Snowflake [documentation](https://docs.snowflake.net/manuals/sql-reference/functions/width_bucket.html):

Constructs equi-width histograms, in which the histogram range is divided into intervals of identical size, and returns the bucket number into which the value of an expression falls, after it has been evaluated. The function returns an integer value or null (if any input is null).
Notes:

**Args:**

- `expr`: The expression for which the histogram is created. This expression must evaluate to a numeric value or to a value that can be implicitly converted to a numeric value.

- `min_value` and `max_value`: The low and high end points of the acceptable range for the expression. The end points must also evaluate to numeric values and not be equal.

- `num_buckets`:  The desired number of buckets; must be a positive integer value. A value from the expression is assigned to each bucket, and the function then returns the corresponding bucket number.

When an expression falls outside the range, the function returns:

- `0` if the expression is less than min_value.
- `num_buckets + 1` if the expression is greater than or equal to max_value.

**Usage:**

```sql
{{ dbt_utils.width_bucket(expr, min_value, max_value, num_buckets) }}
```

## Web macros

### get_url_parameter ([source](macros/web/get_url_parameter.sql))

This macro extracts a url parameter from a column containing a url.

**Usage:**

```sql
{{ dbt_utils.get_url_parameter(field='page_url', url_parameter='utm_source') }}
```

### get_url_host ([source](macros/web/get_url_host.sql))

This macro extracts a hostname from a column containing a url.

**Usage:**

```sql
{{ dbt_utils.get_url_host(field='page_url') }}
```

### get_url_path ([source](macros/web/get_url_path.sql))

This macro extracts a page path from a column containing a url.

**Usage:**

```sql
{{ dbt_utils.get_url_path(field='page_url') }}
```

### url_encode ([source](macros/web/url_encode.sql))

This macro encodes a string to be used in a url.

**Usage:**

```sql
{{ dbt_utils.url_encode('field_to_encode') }}
```

### url_decode ([source](macros/web/url_decode.sql))

This macro decodes a string that was encoded for a url use.

**Usage:**

```sql
{{ dbt_utils.url_decode('field_to_decode') }}
```

----

## Cross-database macros

These macros were removed from `dbt_utils` version 1.0, as they have been implemented in dbt Core instead. See [https://docs.getdbt.com/reference/dbt-jinja-functions/cross-database-macros](https://docs.getdbt.com/reference/dbt-jinja-functions/cross-database-macros).

---

## Jinja Helpers

### pretty_time ([source](macros/jinja_helpers/pretty_time.sql))

This macro returns a string of the current timestamp, optionally taking a datestring format.

```sql
{#- This will return a string like '14:50:34' -#}
{{ dbt_utils.pretty_time() }}

{#- This will return a string like '2019-05-02 14:50:34' -#}
{{ dbt_utils.pretty_time(format='%Y-%m-%d %H:%M:%S') }}
```

### pretty_log_format ([source](macros/jinja_helpers/pretty_log_format.sql))

This macro formats the input in a way that will print nicely to the command line when you `log` it.

```sql
{#- This will return a string like:
"11:07:31 + my pretty message"
-#}

{{ dbt_utils.pretty_log_format("my pretty message") }}
```

### log_info ([source](macros/jinja_helpers/log_info.sql))

This macro logs a formatted message (with a timestamp) to the command line.

```sql
{{ dbt_utils.log_info("my pretty message") }}
```

```shell
11:07:28 | 1 of 1 START table model analytics.fct_orders........................ [RUN]
11:07:31 + my pretty message
```

### slugify ([source](macros/jinja_helpers/slugify.sql))

This macro is useful for transforming Jinja strings into "slugs", and can be useful when using a Jinja object as a column name, especially when that Jinja object is not hardcoded.

For this example, let's pretend that we have payment methods in our payments table like `['venmo App', 'ca$h-money', '1337pay']`, which we can't use as a column name due to the spaces and special characters. This macro does its best to strip those out in a sensible way: `['venmo_app',
'cah_money', '_1337pay']`.

```sql
{%- set payment_methods = dbt_utils.get_column_values(
    table=ref('raw_payments'),
    column='payment_method'
) -%}

select
order_id,
{%- for payment_method in payment_methods %}
sum(case when payment_method = '{{ payment_method }}' then amount end)
  as {{ dbt_utils.slugify(payment_method) }}_amount,

{% endfor %}
...
```

```sql
select
order_id,

sum(case when payment_method = 'Venmo App' then amount end)
  as venmo_app_amount,

sum(case when payment_method = 'ca$h money' then amount end)
  as cah_money_amount,

sum(case when payment_method = '1337pay' then amount end)
  as _1337pay_amount,
...
```
---
## Materializations

### insert_by_period 
In dbt_utils v1.0, this materialization moved to the [experimental features repository](https://github.com/dbt-labs/dbt-labs-experimental-features/tree/main/insert_by_period). 

----

## Reporting bugs and contributing code

- Want to report a bug or request a feature? Let us know by opening [an issue](https://github.com/dbt-labs/dbt-utils/issues/new)
- Want to help us build dbt-utils? Check out the [Contributing Guide](https://github.com/dbt-labs/dbt-utils/blob/main/CONTRIBUTING.md)
  - **TL;DR** Open a Pull Request with 1) your changes, 2) updated documentation for the `README.md` file, and 3) a working integration test. Keep in mind that [most PRs require an approved issue first](https://docs.getdbt.com/community/resources/oss-expectations#pull-requests).

----

## Dispatch macros

**Note:** This is primarily relevant to:

- Users and maintainers of community-supported [adapter plugins](https://docs.getdbt.com/docs/available-adapters)
- Users who wish to override a low-lying `dbt_utils` macro with a custom implementation, and have that implementation used by other `dbt_utils` macros

If you use Postgres, Redshift, Snowflake, or BigQuery, this likely does not apply to you.

[`adapter.dispatch()`](https://docs.getdbt.com/reference/dbt-jinja-functions/adapter#dispatch) provides a reliable way to define different implementations of the same macro across different databases.

In `dbt_project.yml`, you can define a project-level `dispatch` config that enables an "override" setting for all dispatched macros. When dbt searches for implementations of a macro in the `dbt_utils` namespace, it will search through your list of packages instead of just looking in the `dbt_utils` package.

Set the config in `dbt_project.yml`:

```yaml
dispatch:
  - macro_namespace: dbt_utils
    search_order:
      - first_package_to_search    # likely the name of your root project
      - second_package_to_search   # could be a "shim" package, such as spark_utils
      - dbt_utils                  # always include dbt_utils as the last place to search
```

If overriding a dispatched macro with a custom implementation in your own project's `macros/` directory, you must name your custom macro with a prefix: either `default__` (note the two underscores), or the name of your adapter followed by two underscores. For example, if you're running on Postgres and wish to override the behavior of `dbt_utils.safe_add` (such that other macros will use your version instead), you can do this by defining a macro called either `default__safe_add` or `postgres__safe_add`.

Let's say we have the config defined above, and we're running on Spark. When dbt goes to dispatch `dbt_utils.safe_add`, it will search for macros the following in order:

```
first_package_to_search.spark__safe_add
first_package_to_search.default__safe_add
second_package_to_search.spark__safe_add
second_package_to_search.default__safe_add
dbt_utils.spark__safe_add
dbt_utils.default__safe_add
```

----

## Getting started with dbt

- [What is dbt](https://docs.getdbt.com/docs/introduction)?
- Read the [dbt viewpoint](https://docs.getdbt.com/docs/about/viewpoint)
- [Installation](https://docs.getdbt.com/docs/get-started/getting-started/overview)
- Join the [chat](https://www.getdbt.com/community/) on Slack for live questions and support.

## Code of Conduct

Everyone interacting in the dbt project's codebases, issue trackers, chat rooms, and mailing lists is expected to follow the [PyPA Code of Conduct](https://www.pypa.io/en/latest/code-of-conduct/).
