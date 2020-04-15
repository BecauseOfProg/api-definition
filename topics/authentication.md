# Authentication

In order to do some actions, like editing a profile or posting a post, a guest must be authenticated as a user. This authentication step is handled by the /auth endpoint in the API.

In addition to authentications, actions may be locked for users with specific permissions. For more information, check the [dedicated topic](./permissions.md).

**To use authentication in requests that require it, add the `Authorization` header with your token inside.**
