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

- **create** - returns new token (by default expires in 1h)
- **validate** - validates given token and returns _payload_ if success, otherwise _false_
- **middle** - middleware for validating tokens from Authorization header. It successful, sets token property to request object
- **bearerParser** - function to parse Authorization header, returns token if success and empty string otherwise
