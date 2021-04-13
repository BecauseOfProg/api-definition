# Permissions

Permissions are here to say which actions a user can do on the API. A single can have many permissions.

| Name            | Resource                      | Description                          | Granted to                     |
| --------------- | ----------------------------- | ------------------------------------ | ------------------------------ |
| `DEVBLOG_WRITE` | Devblogs                      | Allows writing posts for the devblog | BecauseOfProg members                     |
| `USER_WRITE`    | Users                         | Allow editing any user               | BecauseOfProg members, moderators |
| `BLOG_WRITE`    | Publications                  | Allow writing blog publications.     | BecauseOfProg members, blog editors |
