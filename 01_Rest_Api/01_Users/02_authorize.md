# api/users/authorize (POST)

## Description

Finds user, validates credentials. If credentials are valid, returns new token and user data

|    Note    | Value |
| :--------: | :---: |
| Need Token |  No   |
| Is Public  |  Yes  |

## Request example

| Parameter | Description |
| :-------: | ----------- |
| username  | String      |
| password  | String      |

```js
{
  username: "180101033",
  password: "some-password"
}
```

## Response examples

| HTTP code | Status | Description                      |
| :-------: | :----: | -------------------------------- |
|    200    |  true  | Success, get token and user info |
|    400    | false  | Password is incorrect            |
|    404    | false  | User not found                   |
|    412    | false  | Request conditions are not met   |

### 200 - Success

```js
{
  status: true,
  message: "Success",
  data: {
    token: "token",
    user: {
      username: "some-username",
      language: "user-language",
      roles: [/* list of role ids */],
      widgets: [/* list of widget ids */],
      status: "user status"
    }
  }
}
```

### 400 - Error

```js
{
  status: false,
  message: "Password is incorrect"
}
```

### 404 - Error

```js
{
  status: true,
  message: "User not found"
}
```

### 412 - Request conditions are not met

```js
{
  status: false,
  message: "Request conditions are not met"
}
```
