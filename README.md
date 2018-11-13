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


Simply start it with `graphql init`


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

Check the resulting schema `./schema.graphql`

```sql
# source: https://swapi.graph.cool/
# timestamp: Tue Nov 13 2018 14:29:11 GMT+0100 (CET)

enum _ModelMutationType {
  CREATED
  UPDATED
  DELETED
}

"""Meta information about the query."""
type _QueryMeta {
  count: Int!
}

type AddToFilmPlanetsPayload {
  filmsFilm: Film
  planetsPlanet: Planet
}

type AddToFilmSpeciesPayload {
  filmsFilm: Film
  speciesSpecies: Species
}

type AddToFilmStarshipsPayload {
  filmsFilm: Film
  starshipsStarship: Starship
}
...
```








## GraphiQL

* "Install" GraphiQL using the AppImage:
  * Download the [GrapiQL App Image](https://github.com/skevy/graphiql-app/releases/download/v0.6.3/graphiql-app-0.6.3-x86_64.AppImage)
  * [How to use AppImage in Linux](https://itsfoss.com/use-appimage-linux/)
  * double-click on it to run it
  * open a GraphQL URL and start making requests
      * [online example](https://graphql-compose-swapi.herokuapp.com/?query=%7B%0A%20%20films%20%7B%0A%20%20%20%20title%0A%20%20%20%20episode_id%0A%20%20%20%20opening_crawl%0A%20%20%20%20director%0A%20%20%20%20producer%0A%20%20%20%20release_date%0A%20%20%20%20created%0A%20%20%20%20edited%0A%20%20%20%20url%0A%20%20%7D%0A%7D) 


## Autogenerate your GraphQL schema (as much as possible)

[Wrapping REST with GraphQL](https://www.youtube.com/watch?v=iW4il6wUlvs)

Similar to OpenAPI/Swagger for REST APIs, you might want to avoid writing a GraphQL schema by manually.

A great equivalent to these tools in GraphQL would probably come from the Apollo platform (www.apollographql.com). 


## GraphQL in Python

example:
 * [slides](bit.ly/py-graphql)/[video](https://www.youtube.com/watch?v=cKTbHph-wlk)
    * graphene-python.org




## Build your GraphQL schema from a REST API using GraphQL CLI

Try it with a simple REST API, e.g. http://dummy.restapiexample.com/

Not there yet... (resource to try: https://github.com/apollographql/apollo-link-rest)




## Other References

* [How to wrap a REST API with GraphQL - A 3-step tutorial](https://www.prisma.io/blog/how-to-wrap-a-rest-api-with-graphql-8bf3fb17547d/)
* [Building GraphQL Schema from RESTful API](https://medium.com/@lyskos97/building-graphql-schema-from-rest-api-ee31ac12c57b)
