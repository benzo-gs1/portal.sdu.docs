# Users Service 🖥️

```js
class UsersService {
  static async create(data);
  static async findByUsername(username);
  static validatePasswords(data, encrypted);
  static hashPassword(p);
}
```

- **create** - obtains user data object, hashes his password, saves and returns _new document_ if success, _Mongoose.Error_ otherwise
- **findByUsername** - returns _document_ searched by given username, otherwise returns _null_
- **validatePasswords** - obtains password as `data` and encrypted password as `encrypted`. Returns _true_ if they are equal, _false_ otherwise
- **hashPassword** - returns _hashed password_

## create()

```js
router.post("/some-route", async (req, res) => {
  const data = req.data;
  const result = await UsersService.create(data);

  // if success
  if (result.error) {
    const user = result.user; // user could be accessed
  }

  /* route code */
});
```

## findByUsername()

```js
router.post("/some-router", async (req, res) => {
  const { username } = req.data;

  const user = await UsersService.findByUsername(username);

  // if user is defined
  if (user) {
    // it can be used
  }

  /* route code */
});
```

## validatePasswords()

```js
router.post("/some-router", async (req, res) => {
  const { username, password } = req.data;

  const user = await UsersService.findByUsername(username);

  // if user is defined
  if (user) {
    // we can validate password
    const result = UsersService.validatePasswords(password, user.password);
  }

  /* route code */
});
```

## hashPassword()

```js
const password = "some-password";
const hashedPassword = UsersService.hashPassword(password);
```
