---
layout: api-command 
language: JavaScript
permalink: api/javascript/gt/
command: gt 
github_doc: https://github.com/rethinkdb/docs/edit/master/2-query-language/api/javascript/math-and-logic/gt.md
io:
    -   - value
        - bool
related_commands:
    eq: eq
    ne: ne/
    ge: ge/
    lt: lt/
    le: le/
---

{% apibody %}
value.gt(value) → bool
{% endapibody %}

Test if the first value is greater than other.

__Example:__ Is 2 greater than 2?

```js
r.expr(2).gt(2).run(conn, callback)
```

