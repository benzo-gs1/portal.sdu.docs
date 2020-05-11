# api/token/validate (POST)

## Description

Validates token from Authorization: Bearer &lt;token> pattern

|    Note    |  Value  |
| :--------: | :-----: |
| Need Token | **Yes** |
| Test route |   No    |
| Is Public  | **Yes** |

## Request example

| Parameter | Description       |
| :-------: | ----------------- |
|   token   | Token to validate |

```http
<!-- other headers -->

Authorization: Bearer 1f2efaf79922904c5ce829950aeed941a17a714e20bc9e22a9bd

<!-- other headers -->
```

## Response

| Response Status code | Description        |
| :------------------: | ------------------ |
|         200          | True, token passed |
|         401          | No Token           |
|         403          | Unauthorized       |

### Example - 200

```js
{
  status: true,
  message: "Token Validated"
}
```

### 401 - No Token

```js
{
  status: false,
  message: "No token presented"
}
```

### 403 - Unauthorized

```js
{
  status: false,
  message: "Bad token"
}
```
