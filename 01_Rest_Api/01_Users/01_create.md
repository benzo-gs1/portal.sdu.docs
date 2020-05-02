# api/users/create (POST)

## Description

Creates user from given credentials and returns it

|    Note    |  Value  |
| :--------: | :-----: |
| Need Token |   No    |
| Test route | **Yes** |

## Request example

Send parameters related to Users' Schema. See [User Model](../../05_Database/Documents/Users.md)

```js
{
  username: "180101033",
  password: "thisisapassword",
  language: "en"
  // other parameters
}
```

## Response

| Response Status code | Description |
| :------------------: | ----------- |
|         200          | Success     |
|         400          | Error       |

### Example - 200

```js
{
  status: true,
  user: {
    // created user
  }
}
```

### Example - 400

```js
{
  status: false,
  message: "Fail, verify your data"
}
```
