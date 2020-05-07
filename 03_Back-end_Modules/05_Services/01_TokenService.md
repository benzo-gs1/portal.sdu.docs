# Token Service 🎫

This service provides following methods:

```ts
class TokenService {
  static create(data: ITokenData, lifetime = "1h"): string | false;
  static validate(token: string): ITokenData | false;
  static bearerParser(header: express.Request): string | false;
}
```

**ITokenData:** interface, describing data encapsulated into user token:

```ts
export interface ITokenData {
  ip: string;
  username: string;
  role_level: number;
}
```

- **create** - returns _token_ string on given _data_ or false in case of error
- **validate** - returns _data_ encapsulated inside given _token_ or false in case of error
- **bearerParser** - returns _token_ string parsing http authorization header from given express _request_ object or false in case of error

## create()

```ts
const data: ITokenData = {
  role_level: 0,
  username: "some-username",
  ip: "some-ip",
};

const token: string | false = TokenService.create(data); // new token, expires in 1 hour by default
```

## validate()

```ts
const token: string = "some-token";

const result: ITokenData | false = TokenService.validate(token); // result is data given in generation process or false
```

## bearerParser()

```ts
router.post("/some-route", (req: express.Request, res: express.Response) => {
  // Returns token, parsed from Authorization header
  const token: string | false = TokenService.bearerParser(req);
});
```
