# api/users/create (POST)

In development, creates user from given credentials and returns it

| Parameter | Description                               |
| :-------: | ----------------------------------------- |
| username  | User's login (unique id or username)      |
| password  | User's password                           |
| language  | User's chosen language (default: English) |
|   role    | User's role                               |

### Request example

```json
{
  "username": "180101033",
  "password": "thisisapassword",
  "language": "en",
  "role": "student"
}
```

| Response Status code | Description |
| :------------------: | ----------- |
|         200          | Success     |
|         406          | Error       |

### Response example (Success)

HTTP Code: 200

```json
{
  "status": true,
  "user": {
    // created user
  }
}
```

### Response example (Fail)

HTTP code: 406

```json
{
  "status": false,
  "error": {
    // mongoose error
  }
}
```
