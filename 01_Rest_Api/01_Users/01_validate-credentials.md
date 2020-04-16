# api/users/validate-credentials (POST)

## Description

Validating user credentials

|    Note    | Value |
| :--------: | :---: |
| Need Token |  No   |
| Test route |  No   |

## Request example

| Parameter | Description                          |
| :-------: | ------------------------------------ |
| username  | User's login (unique id or username) |
| password  | User's password                      |

```json
{
  "username": "180101033",
  "password": "thisisapassword"
}
```

## Response example (Fail)

| Response Status code | Description           |
| :------------------: | --------------------- |
|         200          | Success               |
|         404          | User not found        |
|         406          | Password is incorrect |

HTTP code: 406

```json
{
  "status": false,
  "error": "Password is incorrect"
}
```
