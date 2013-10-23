---
layout: api-command 
language: JavaScript
permalink: api/javascript/union/
command: union 
github_doc: https://github.com/rethinkdb/docs/edit/master/2-query-language/api/javascript/transformations/union.md
io:
    -   - sequence
        - array
---

{% apibody %}
sequence.union(sequence) → array
{% endapibody %}

Concatenate two sequences.

__Example:__ Construct a stream of all heroes.

```js
r.table('marvel').union(r.table('dc')).run(conn, callback)
```
