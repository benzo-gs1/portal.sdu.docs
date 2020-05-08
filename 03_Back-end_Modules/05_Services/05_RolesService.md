# Roles Service 🙎‍♂️

This service provides following methods:

```js
const roles: IRole[] = [/* list of roles */];

class RolesService {
  static authorize(role_level: number, api: string): boolean;
}
```

Roles array holds existing roles by their level. IRole interface:

```ts
export interface IRole {
  level: number;
  title: string;
  actions: string[];
}
```

Where level describes it's index in the roles array. Title is just a name to it. Actions, array of patterns of allowed api end points, example:

- `api/users/*` - allow every route in the api/users path
- `api/users/fetch` - allow exact route
- `api/*/fetch` - allow anything between api and fetch paths. e.g. api/posts/fetch, api/users/fetch

- **authorize** - returns _true_ if given role is allowed to access routePath specified. Otherwise returns _false_

## authorize

```ts
// check if user student is allowed to api/users/fetch
const result = RolesService.authorize(0, "api/users/fetch");

console.log(result); // true or false
```
