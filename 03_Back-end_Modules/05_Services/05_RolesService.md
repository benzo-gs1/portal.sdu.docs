# Roles Service 🙎‍♂️

This service provides following methods:

```js
class RolesService {
  static authorize(routePath, role_level);
}
```

- **authorize** - returns _true_ if given role is allowed to access routePath specified. Otherwise returns _false_

## authorize

```js
// check if user student is allowed to api/users/fetch
const result = RolesService.authorize("api/users/fetch", 0);

console.log(result); // true or false
```
