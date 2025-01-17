---
id: '8base-console-graphql-api-queries-related-record-query'
sidebar_label: 'Related Record Query'
redirect_from: '/backend/graphql-api/queries/related-record-query'
slug: '/projects/backend/graphql-api/queries/related-record-query'
---

# Related Record Query

_For the sake of the following examples, let's consider a scenario where a table called `Posts` exists, having expected fields and relations like `title`, `body`, `author`, etc._

## Fetching related table records

Query a single record and return data from related tables in the response.

<div class="code-sample">
<div>
<label>Request</label>

```javascript
query {
  post(title: "Awesome Possum") {
    title
    author {
      name
      avatar {
        downloadUrl
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
    "post": {
      "title": "Awesome Possum",
      "author": {
        "name": "Huxley",
        "avatar": {
          "downloadUrl": "https://linktomy.downloadUrl/forA/amazingAvatar.jpg"
        }
      }
    }
  }
}
```

</div>
</div>
