# api/users/validate (POST)

## Description

Validating user's credentials

|    Note    | Value |
| :--------: | :---: |
| Need Token |  Yes  |
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

| HTTP code | Status | Description                    |
| :-------: | :----: | ------------------------------ |
|    200    |  true  | Success, credentials are valid |
|    400    | false  | Password is incorrect          |
|    404    | false  | User not found                 |
|    412    | false  | Request conditions are not met |

### 200 - Success

```js
{
  status: true,
  message: "Credentials are valid"
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
