# Connection

This document describes, how mongoose connection is handled.

We define IConnection interface:

```ts
export interface IConnection {
  slow: mongoose.Connection;
  fast: mongoose.Connection;
}
```

We use two connections for slow and fast queries with poolSize of 10 in production mode enabled.

## Models

We are creating two models for both slow and fast connections

```ts
// models/example/index.ts

import IExampleSchema from "./interface.ts";
import ExampleSchema from "./schema.ts";
import config from "@/config";
import { ModelNames } from "@/@types";

export default {
  slow: config.connection.slow.model(ModelNames.EXAMPLES),
  fast: config.connection.slow.model(ModelNames.EXAMPLES),
};
```
