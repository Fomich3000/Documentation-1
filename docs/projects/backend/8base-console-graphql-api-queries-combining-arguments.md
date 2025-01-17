---
id: '8base-console-graphql-api-queries-combining-arguments'
sidebar_label: 'Combining Arguments'
redirect_from: '/backend/graphql-api/queries/combining-arguments'
slug: '/projects/backend/graphql-api/queries/combining-arguments'
---

# Combining Arguments

_For the sake of the following examples, let's consider a scenario where a table called `Posts` exists, having expected fields and relations like `title`, `body`, `author`, etc._

## Using multiple arguments in queries

More than one argument can get used in a single list query.

<div class="code-sample">
<div>
<label>Request</label>

```javascript
query {
  postsList(filter: {
    title: {
      contains: "Possum"
    }
  },
  sort: {
    title: ASC
  },
  first: 2,
  skip: 0
  ) {
    items {
      title
      createdAt
      author {
        name
      }
    }
  }
}
```

</div>
<div>
<label>Response</label>

```json
{
  "data": {
    "postsList": {
      "items": [
        {
          "title": "Awesome Possum",
          "createdAt": "2019-09-04T22:11:18.493Z",
          "author": {
            "name": "Huxley"
          }
        },
        {
          "title": "Everybody Loves Possum",
          "createdAt": "2019-09-04T22:26:19.045Z",
          "author": {
            "name": "Stevens"
          }
        }
      ]
    }
  }
}
```

</div>
</div>
