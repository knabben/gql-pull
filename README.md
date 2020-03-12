GraphQL pull
===

An action for pulling a schema from GraphQL via introspection and converting to a Graph in
a SQLite3 database.

This Github Action uses [knabben/ggql](https://github.com/knabben/ggql)

Input
---

url: The GraphQL endpoint URL.

Output
---

output: The difference of both schemas in a formatted string.

Usage Example
---

It is possible to pass a source and destination to make the comparision, between two schemas,
an URL or a JSON file is allowed.

```
- name: gql-pull
  id: gql
  uses: knabben/gql-pull@0.0.6
  with:
    source: http://www.example.com/graphql/
    destination: web/pr-schema.json

- name: Bring diff to PR
  uses: unsplash/comment-on-pr@master
  with:
    msg: ${{ steps.gql.outputs.output }}
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```


