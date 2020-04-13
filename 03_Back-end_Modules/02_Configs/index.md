# Configs ⚙️

This document describes configurations of the system.

## Environment

- PORT - server port
- ENV_MODE - mode for system (dev, prod)
- TOKEN_ALGORITHM - algorithm for token creation
- USER_TOKEN_SECRET - secret key for jwt
- MONGODB_URI - mongodb uri

## JSON interpretation

Values are loaded from .env file and are available using `import config from "@/config";`

```js
{
  port: Number,
  isProduction: Boolean,
  secretAlgorithm: String,
  secretKey: String,
  mongodbUri: String,
  server: Object,
  connection: Object
}
```
