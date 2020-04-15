# Change log

This is a list of all the changes that affected the API since its launch. Updates are sorted by decreasing date.

## Updated : return data clarification

**May 30, 2019 :** All returned data is now in a `data` list / object.

## Added : Get all users

**May 30, 2019 :** Users with the `USER_WRITE` permission can now get all other users.

## Added : Blog posts endpoint

**May 30, 2019 :** You can now access to blog posts via a new endpoint.

## Changed : Optional fields

**April 9, 2019 :** All the fields in some PATCH requests are now optional, meaning that you can only include fields that you're going to edit.

**Affecting :** Edit user's profile, Edit post.

## Added : User's informations with post

**April 9, 2019 :** when a post is returned, all the users informations are returned.

**Affecting :** Post resource

## Added : Get user's permissions

**January 5, 2019 :** getting user's permissions is now in `/users/{username}/permissions` and requires `USER_WRITE` permission.

**Affecting :** Get user

## Changed : `avatar` is now `picture`

**January 5, 2019 :** user field `avatar` has been renamed into `picture`.

**Affecting :** Get user, Edit user's profile

## Added : /users/{username}/permissions

**January 5, 2019 :** added the possibility to edit user's permissions.

## Added : `USER_WRITE` and `BLOG_WRITE` permissions

**January 5, 2019 :** updated permissions list to add these two permissions.

## Updated : Modify user request's parameters change

**January 5, 2019 :** `avatar` added and `email` removed.

## Breaking change : Auth now in a header

**September 24, 2018 :** The token should be passed in the `Authorization` header of the request.

## Removed : Access to all users

**September 8, 2018 :** The /users endpoint with GET method is no longer available.

## Breaking change : root is now /v1

**September 7, 2018 :** To have more clarity, the root URL is no longer /api, but /v1.
