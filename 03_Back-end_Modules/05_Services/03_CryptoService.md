# Users Service 🖥️

```ts
class CryptoService {
  static validatePasswords(data: string, encrypted: string): boolean;
  static hashPassword(p): string;
}
```

- **validatePasswords** - returns _true_ or _false_ whether given _data_ is equal _encrypted_ string
- **hashPassword** - returns hashed and salted _password_ from given _p_

## validatePasswords()

```ts
const password = "thisisapassword";
const encrypted = "hash";

const result: boolean = CryptoService.validatePasswords(password, encrypted); // true or false
```

## hashPassword()

```ts
const password = "some-password";
const hashedPassword: string = UsersService.hashPassword(password); // hashed password
```
