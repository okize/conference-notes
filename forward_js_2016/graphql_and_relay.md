# GraphQL & Relay

### Samer Buna

===

## GraphQL

https://learngraphql.com/

http://graphql.org/docs/api-reference-graphql/

#### What is it?

* Data query language & runtime
* is a whole new language
* provides a layer between app and database sever
* the best thing from the client perspective is the declarative style of data requirements

* `curly brace` are called query sets
* any database is a graph data structure (tree is a special version of a graph)

the `connection` interface is for pagination

if you don't specify the type of the operation, the default is a query operation

you should normally name your queries

query is for read operations
mutation is for create, update, delete operations
subscription is used for real-time operations (using sockets)
fragments are the compositional components of GraphQL; fragments can use fragments

fields can support aliases



to work with GraphQL, a schema is your starting point; this is what you want to expose from your database

the schema is just the description, to use it we need an interface

GraphQL has no requirement to run as an http server; could use sockets, readlines, http, etc



GraphQL context object (ie. global)
* currently authenticated user
* database connections

https://github.com/RGRjs/rgrjs.com

solve GraphQL `n + 1` problem with `batching`

https://github.com/facebook/dataloader