# Token Service 🎫

This service provides following methods:

```js
class TokenService {
  static create(data={}, lifetime="1h");
  static validate(token);
  static middle(req, res, next);
  static bearerParser(header);
}
```

- **create** - creates new token (by default expires in 1h)
- **validate** - validates given token
- **middle** - middleware for validating tokens from Authorization header. It successful, sets token property to request object
- **bearerParser** - function to parse Authorization header
