---
layout: api-command 
language: JavaScript
permalink: api/javascript/row/
command: row
rb: false
io:
    -   - r
        - value
---

# Command syntax #

{% apibody %}
r.row &rarr; value
{% endapibody %}

# Description #

Returns the currently visited document.

__Example:__ Get all users whose age is greater than 5.

```js
r.table('users').filter(r.row('age').gt(5)).run(conn, callback)
```


__Example:__ Accessing the attribute 'child' of an embedded document.

```js
r.table('users').filter(r.row('embedded_doc')('child') > 5).run(conn, callback)
```


__Example:__ Add 1 to every element of an array.

```js
r.expr([1, 2, 3]).map(r.row.add(1)).run(conn, callback)
```


__Example:__ For nested queries functions should be used instead of r.row.

```js
r.table('users').filter(function(doc) {
    return doc('name').eq(r.table('prizes').get('winner'))
}).run(conn, callback)
```

