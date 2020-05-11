# api/token/test/generate (POST)

## Description

Generates token from given payload

|    Note    |  Value  |
| :--------: | :-----: |
| Need Token |   No    |
| Test route | **Yes** |
| Is Public  | **Yes** |

## Request example

```js
{
  ip: "some-ip address",
  role_level: 0,
  username: "some-username"
}
```

## Response example

| Response Status code | Description                    |
| :------------------: | ------------------------------ |
|         200          | Success                        |
|         412          | Request conditions are not met |

HTTP Code: 200

```js
{
  token: "generated-token",
}
```
