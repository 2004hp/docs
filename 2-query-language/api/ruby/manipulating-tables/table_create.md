---
layout: api-command 
language: Ruby
permalink: api/ruby/index_create/
command: index_create 
github_doc: https://github.com/rethinkdb/docs/edit/master/2-query-language/api/ruby/manipulating-tables/table_create.md
---

{% apibody %}
table.index_create(index_name[, index_function]) → object
{% endapibody %}

Create a new secondary index on this table.

__Example:__ To efficiently query our heros by code name we have to create a secondary
index.

```rb
r.table('dc').index_create('code_name').run(conn)
```

__Example:__ A compound index can be created by returning an array of values to use as
the secondary index key.

```rb
r.table('dc').index_create('parental_planets') {|hero|
    [hero['mothers_home_planet'], hero['fathers_home_planet']]
}.run(conn)
```


__Example:__ A multi index can be created by passing an optional multi argument. Multi
indexes functions should return arrays and allow you to query based on whether a value
is present in the returned array. The example would allow us to get heroes who possess
a specific ability (the field 'abilities' is an array).


```rb
r.table('dc').index_create('abilities', :multi => true).run(conn)
```

