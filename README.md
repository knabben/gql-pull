GraphQL Pull and Compare
===

An action that pulls the schema from a source and destination GraphQL endpoint via introspection or file, converts both schemas in graphs and compare the fields and arguments reproducing the result in a comment in your PR. 

This Github Action uses [knabben/ggql](https://github.com/knabben/ggql)

Input
---

* source: The GraphQL endpoint or file to be compared from.
* destination: The GraphQL endpoint or file to be compared with.

Output
---

* output: The difference of both schemas in a formatted string.

Usage Example
---


<img width="764" alt="screen" src="https://user-images.githubusercontent.com/1223213/77980416-3cb02a00-72d5-11ea-92e5-063c9259ff53.png">

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


