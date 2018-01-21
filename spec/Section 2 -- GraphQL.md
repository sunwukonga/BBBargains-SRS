# GraphQL Schema

This is the glue that links the server backend to the mobile front-end.

```graphql example
type Lister {
  name: String
  age: Int
  picture: Url
}
  listing(id: 4) {
    title
    description
    image-resource
  }
}
```

Which would return the following JSON data:

```json example
{
  "listing": {
    "title": "Applejack"
    "description": "Sleep aid. A tablespoon before bed will put your littl'n to
sleep for the count"
    "ourimageserver.com/collection/xxxxxxx"
  }
}
```
