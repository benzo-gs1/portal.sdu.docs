# api/token/validate (GET)

Validates token from Authorization: Bearer &lt;token> pattern

| Parameter | Description       |
| :-------: | ----------------- |
|   token   | Token to validate |

### Request example

```http
<!-- other headers -->

Authorization: Bearer 1f2efaf79922904c5ce829950aeed941a17a714e20bc9e22a9bd

<!-- other headers -->
```

| Response Status code | Description         |
| :------------------: | ------------------- |
|         200          | True, token passed  |
|         406          | False, token failed |

### Response example (Success)

HTTP Code: 200

```json
{
  // payload
}
```

### Response example (Fail)

HTTP code: 406

```http
Unauthorized
```
