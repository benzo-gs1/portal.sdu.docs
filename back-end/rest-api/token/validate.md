# api/token/validate (POST)

Validating token

| Parameter | Description       |
| :-------: | ----------------- |
|   token   | Token to validate |

### Request example

```json
{
  "token": "1f2efaf79922904c5ce829950aeed941a17a714e20bc9e22a9bd"
}
```

| Response Status code | Description         |
| :------------------: | ------------------- |
|         200          | True, token passed  |
|         406          | False, token failed |

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
  "status": false
}
```
