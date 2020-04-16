# api/token/generate (POST)

## Description

Generates token from given payload

|    Note    | Value |
| :--------: | :---: |
| Need Token |  No   |
| Test route |  Yes  |

## Request example

```json
{
  // any payload
}
```

## Response example

HTTP Code: 200

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IlJheURhcmFyIiwiaWF0IjoxNTg0ODc0OTU1LCJleHAiOjE1ODQ4Nzg1NTV9.opOkiaErjUmjhXkMUMI_7SC-rKUGRpWQxdiLEblPhig"
}
```
