---
layout: api-command 
language: JavaScript
permalink: api/javascript/group_by/
command: groupBy
---

{% apibody %}
sequence.groupBy(selector1[, selector2...], reductionObject) → array
{% endapibody %}

Groups elements by the values of the given attributes and then applies the given
reduction. Though similar to `groupedMapReduce`, `groupBy` takes a standardized object
for specifying the reduction. Can be used with a number of predefined common reductions.

__Example:__ Using a predefined reduction we can easily find the average strength of members of each weight class.

```js
r.table('marvel').groupBy('weightClass', r.avg('strength')).run(conn, callback)
```


__Example:__ Groupings can also be specified on nested attributes.

```js
r.table('marvel').groupBy({'abilities' : {'primary' : true}}, r.avg('strength')).run(conn, callback)
```


__Example:__ The nested syntax can quickly become verbose so there's a shortcut.

```js
r.table('marvel').groupBy({'abilities' : 'primary'}, r.avg('strength')).run(conn, callback)
```

