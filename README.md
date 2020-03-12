GraphQL pull
===

An action for pulling a schema from GraphQL via introspection and converting to a Graph in
a SQLite3 database.

This Github Action uses [knabben/ggql](https://github.com/knabben/ggql)

Input
---

url: The GraphQL endpoint URL

Usage Example
---

It is possible to pass a source and destination to make the comparision, between two schemas,
an URL or a JSON file is allowed.

```
- name: gql-pull
  uses: knabben/gql-pull@0.0.1
  with:
    source: schema.json
    destination: dest.json
```