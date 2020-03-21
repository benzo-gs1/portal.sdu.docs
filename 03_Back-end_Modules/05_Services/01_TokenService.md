# Token Service 🎫

This service provides following methods:

```js
class TokenService {
  static create(data, lifetime);
  static validate(token);
  static middle(req, res, next);
}
```

- **create** - creates new token
- **validate** - validates given token
- **middle** - middleware for validating tokens from cookies
