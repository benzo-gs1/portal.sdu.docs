# api/users/create (POST)

## Description

Creates user from given credentials and returns it

|    Note    | Value |
| :--------: | :---: |
| Need Token |  No   |
| Test route |  Yes  |

## Request example

Send parameters related to Users' Schema. See [User Model](../../05_Database/Documents/Users.md)

```json
{
  "username": "180101033",
  "password": "thisisapassword",
  "language": "en"
  // other parameters
}
```

## Response example (Success)

| Response Status code | Description |
| :------------------: | ----------- |
|         200          | Success     |
|         406          | Error       |

HTTP Code: 200

```json
{
  "status": true,
  "user": {
    // created user
  }
}
```
