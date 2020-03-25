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

- **create** - returns _new token_ (by default expires in 1h)
- **validate** - validates given token and returns _data_ if success, otherwise _false_
- **middle** - middleware for validating tokens from Authorization header. It successful, sets token property to request object
- **bearerParser** - function to parse Authorization header, returns _token_ if success and _empty string_ otherwise

## create()

```js
const data = {
  role: "student"
};

const token = TokenService.create(data); // new token, expires in 1 hour by default
```

## validate()

```js
const token = "some-token";

const result = TokenService.validate(token); // result is data given in generation process or false
```

## middle()

```js
router.post("/route-to-check", TokenService.middle, (req, res) => {
  const token = req.token; // token could be accessed
  // route code
});
```

## bearerParser()

```js
router.post("/some-route", (req, res) => {
  // Returns token, parsed from Authorization header
  const token = TokenService.bearerParser(req.headers["authorization"]);
});
```
