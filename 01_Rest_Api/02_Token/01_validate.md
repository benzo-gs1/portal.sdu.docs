# api/token/validate (POST)

## Description

Validates token from Authorization: Bearer &lt;token> pattern

|    Note    |  Value  |
| :--------: | :-----: |
| Need Token | **Yes** |
| Test route |   No    |

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

| Response Status code | Description         |
| :------------------: | ------------------- |
|         200          | True, token passed  |
|         406          | False, token failed |

### Example - 200

```js
{
  status: true,
}
```

### Example - 406

```js
{
  status: false,
  message: "Token failed"
}
```
