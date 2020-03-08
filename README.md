GraphQL pull
===

An action for pulling a schema from GraphQL via introspection and converting to a Graph in
a SQLite3 database.

This Github Action uses [knabben/ggql](https://github.com/knabben/ggql)

Input
---

url: The GraphQL endpoint URL

Output
---

file: The path of the SQLite3 database