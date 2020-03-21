# api/users/validate-credentials (POST)

Validating user credentials

| Parameter | Description                          |
| :-------: | ------------------------------------ |
| username  | User's login (unique id or username) |
| password  | User's password                      |

### Request example

```json
{
  "username": "180101033",
  "password": "thisisapassword"
}
```

| Response Status code | Description           |
| :------------------: | --------------------- |
|         200          | Success               |
|         404          | User not found        |
|         406          | Password is incorrect |

### Response example (Success)

HTTP Code: 200

```json
{
  "status": true
}
```

### Response example (Fail)

HTTP code: 406

```json
{
  "status": false,
  "error": "Password is incorrect"
}
```
