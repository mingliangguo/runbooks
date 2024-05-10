# DBT


## DBT cheat-sheet

- https://datacoves.com/post/dbt-jinja-functions-cheat-sheet

## DBT jinja cheat sheets

#### convert a list to a comma separated string, each is wrapped with single quotes, a typical use case is to convert a list to an in-clause

```jinja
{% set col_list = ['a', 'b', 'c'] %}
{{ "'" ~ col_list |join("','") ~ "'" }}
```

**NOTE** the caveat of the implementation is that it only works with non-empty list (otherwise the in query will fail.)

