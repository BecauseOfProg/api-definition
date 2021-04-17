# Pagination

Some requests can return a lot of database entries, that make the client request slower and the API overloaded. To overcome this problem, endpoints in question integrate a system to prevent overloaded responses.

**By default, the first `X` entries are returned** (X is defined for each entity). To get the next `x` entries, you must add the `skip` query parameter. Moreover, you can pass the `size` param to get less entities (from 1 to `X`). The total amount of entities is available under the `Count` header. If you go past this number, the data will obviously be empty.
