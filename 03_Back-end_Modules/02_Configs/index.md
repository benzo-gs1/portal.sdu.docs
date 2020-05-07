# Configs ⚙️

This document describes configurations of the system.

## Environment

- PORT - server port
- NODE_ENV - mode for system (development, production)
- TOKEN_ALGORITHM - algorithm for token creation
- USER_TOKEN_SECRET - secret key for jwt
- MONGODB_URI - mongodb uri

## IConfig interface

Configuration object is available using `import config from "@/config";`.

**Note:** `init` method is called once at the loading process
**Note:** `setConfig` method is being used to set new configuration data or use config as singleton object

```ts
export interface IConfig {
  port: number;
  isProduction: boolean;
  secretAlgorithm: string;
  secretKey: string;
  mongodbUri: string;
  mongoConnection?: IConnection;
  server?: Server;
  isTesting?: boolean;
  [index: string]: any;
  setConfig: (key: string, value: any) => void;
  init: () => void;
}
```
