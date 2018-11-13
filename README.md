# GraphQL & GraphQL CLI

## GraphQL in a nutshell

> * **Describe your data** (a query language for your API)
> * **Ask for what you want** (simpler query than complex RESP api requests)
> * **Get predictable results** (get back **only** what you asked for, not the typical extra properties/attributes you don't care about! )

ex. 

* You want to fetch data from your favorite API (e.g. the Youtube API)
* GraphQL simplifies the way you interact with a classis REST API
* The GraphQL server will take in your API as a series of "type definitions", defining the shape of your data.
* You write your queries as "resolvers"
* the GraphQL server takes all that and exposes your GraphQL API via an endpoint
* It reduces the amount of trips you do to the API itself. With GraphQL, you hit **one* endpoint then ask what you want!

Also, GraphQL is **just a specification**, not an implementation of this great idea. So there is actually a bunch of implementations around it and competition to build it.


Beside server's implementation, there is also "client" libraries as the Front-end component of it (ex [Apollo Client](https://www.apollographql.com/docs/react/) by Medium, or [Relay](https://facebook.github.io/relay/) by Facebook, or [GQL](https://github.com/graphql-python/gql), a GraphQL client in Python).


To learn more and test online: [GraphiQL](https://github.com/graphql/graphiql) (An in-browser IDE for exploring GraphQL.)




## GraphQL CLI

https://github.com/graphql-cli/graphql-cli


```shell
(gcp) patrick@cx18:~/Documents/dev/graphQL_test$ graphql init
? Enter project name (Enter to skip): swapi
? Local schema file path: schema.graphql
? Endpoint URL (Enter to skip): https://swapi.graph.cool/
? Name of this endpoint, for e.g. default, dev, prod: default
? Subscription URL (Enter to skip): 
? Do you want to add other endpoints? No
? What format do you want to save your config in? JSON

About to write to /home/patrick/Documents/dev/graphQL_test/.graphqlconfig:

{
  "projects": {
    "swapi": {
      "schemaPath": "schema.graphql",
      "extensions": {
        "endpoints": {
          "default": "https://swapi.graph.cool/"
        }
      }
    }
  }
}

? Is this ok? Yes
(gcp) patrick@cx18:~/Documents/dev/graphQL_test$
```



```shell
(gcp) patrick@cx18:~/Documents/dev/graphQL_test$ graphql  get-schema
project swapi - endpoint default - Schema file was created: schema.graphql
(gcp) patrick@cx18:~/Documents/dev/graphQL_test$
```