---
layout: api-command 
language: Ruby
permalink: api/ruby/append/
command: append 
github_doc: https://github.com/rethinkdb/docs/edit/master/2-query-language/api/ruby/document-manipulation/append.md
related_commands:
---

{% apibody %}
array.append(value) → array
{% endapibody %}

Append a value to an array.

__Example:__ Retrieve Iron Man's equipment list with the addition of some new boots.

```rb
r.table('marvel').get('IronMan')[:equipment].append('new_boots').run(conn)
```


