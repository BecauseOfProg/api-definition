# Permissions

Permissions indicate which actions a user can do on the API. A single one can have many permissions.

| Name            | Bitwise value | Resource                      | Description                          | Granted to                     |
| --------------- | ----------------------------- | ------------------------------------ | ------------------------------ |
| `USER_WRITE`    | 2             |  Users                         | Allow editing any user               | BecauseOfProg members, moderators |
| `BLOG_WRITE`    | 4             | Publications                  | Allow writing blog publications.     | BecauseOfProg members, blog writters |
| `DEVBLOG_WRITE` | 8             | Devblogs                      | Allows writing posts for the devblog | BecauseOfProg members                     |
