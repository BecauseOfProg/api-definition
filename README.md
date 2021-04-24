<div align="center">
  <img src="https://cdn.becauseofprog.fr/v2/sites/becauseofprog.fr/assets/logos/bop.min.svg" alt="Logo BecauseOfProg"  width="150"/>
  <h1>BecauseOfProg's API</h1>
  <h3>Fetch all kind of informations related to the BecauseOfprog</h3>
</div>

Welcome on the BecauseOfProg's API ! From there, you can fetch data available on our website :

- Users registered on the website
- Publications written on the blog and the devblogs
- Comments submitted by users on publications

First of all, you need a URL in order to access it. The root URL for the API is `https://api.becauseofprog.fr`. This URL is followed by the version of this format : `v{number}`. You can find versions below:

| Version | Status     |
| ------- | ---------- |
| 2       | Available  |
| 1       | Depecrated |

## Requests

Every request to the API that require a body must be JSON-formatted, with the `Content-Type` header properly set to `application/json`: otherwise, a `400 Bad Request` status is returned.

### Authentication

To access some endpoints, the user must be authenticated by grabbing its token on the `/auth` endpoint. This token is placed in the `Authorization` header of the request in question. If the user isn't authenticated when this is mandatory, a `401 Unauthorized` status is returned.

### Permissions

Permissions indicate which actions a user can do on the API. A single one can have many permissions.

| Name            | Bitwise value | Resource                      | Description                          | Granted to                     |
| --------------- | ----------------------------- | ------------------------------------ | ------------------------------ |
| `USER_WRITE`    | 2             |  Users                         | Allow editing any user               | BecauseOfProg members, moderators |
| `BLOG_WRITE`    | 4             | Publications                  | Allow writing blog publications.     | BecauseOfProg members, blog writters |
| `DEVBLOG_WRITE` | 8             | Devblogs                      | Allows writing posts for the devblog | BecauseOfProg members                     |

If the user doesn't have the required permission on an endpoint, a `403 Forbidden` status is returned.

### Rate limiting

In order to prevent spamming on the API, a system limits the number of possible requests per time interval. This is all detailed in response headers:

- The `X-Ratelimit-Limit` header provides the maximum number of requests possible before limiting
- The `X-Ratelimit-Remaining` header indicates the number of remaining requests
- The `X-Ratelimit-Reset` is the number of seconds remaining before the number of possible requests returns back to the allowed amount

**By default, the limit of requests is 5 and the time interval is 5 seconds.** If this limit is reached, a `429 Too Many Requests` status is returned.

## Responses

Every response is in JSON format (with `Content-Type` header properly set to `application/json`), either an object or an array depending on the endpoint. Data can be empty, especially for entity creation or deletion.

### Pagination

Some requests can return a lot of database entries, that make the client request slower and the API overloaded. To overcome this problem, endpoints in question integrate a system to prevent overloaded responses.

**By default, the first `X` entries are returned** (X is defined for each entity). To get the next `x` entries, you must add the `skip` query parameter. Moreover, you can pass the `size` param to get less entities (from 1 to `X`). The total amount of entities is available under the `Count` header. If you go past this number, the data will obviously be empty.
