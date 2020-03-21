# Configs ⚙️

This document describes configurations of the system.

## Environment

- PORT - server port
- ENV_MODE - mode for system (dev, prod)
- TOKEN_ALGORITHM - algorithm for token creation
- USER_TOKEN_SECRET - secret key for jwt

## JSON interpretation

```json
{
  "port": Integer,
  "isProduction": Boolean,
  "secret": {
    "user": String,
    "algorithm": String
  }
}
```
