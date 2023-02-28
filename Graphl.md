# GraphQL API Notes

GraphQl is a query language for data APIs, from a perspective of a frontend consumer.

GraphQl common issues are

1. Information Disclosure
2. Denial of service
3. Authentication and Authorization Flaws
4. Injections
    - Command injections
    - header injections
    - SQL injections
    - HTML injections

## 1. Introspection Query

-   Introspective queries start with a root field that's either `__type` or `__schema` known as meta fields.
-   `__schema` field is used to read information about the API schema, such as types and directives it supports.

```graphql
query {
    __schema {
        queryType {
            name
        }
        mutationType {
            name
        }
        subscriptionType {
            name
        }
        types {
            kind
            name
            fields {
                name
                args {
                    name
                }
            }
        }
    }
}
```

## 2. Field types identification

```graphql
query {
    __type(name: "Login") {
        name
        kind
        fields {
            name
            type {
                name
                kind
            }
        }
    }
}
```

## 3. Subscriptions operations

-   Used for real-time communication between the server and client

```graphql
query {
    __schema {
        subscriptionType {
            name
            kind
            fields {
                name
                description
            }
        }
    }
}
```

## 4. Mutation Operations

```graphql
query {
    __schema {
        mutationType {
            name
            kind
            fields {
                name
                description
            }
        }
    }
}
```

## 5. Common graphQl endpoints

1. /graphql
2. /graphiql
3. /playground

## 6. GraphQL directives

-   directive is any string in a GraphQL document that begins with the `@` character
-   built-in directives are @include, @skip, @deprecated

```graphql
query {
    __schema {
        directives {
            name
            description
            locations
            args {
                name
                description
                defaultValue
            }
        }
    }
}
```
