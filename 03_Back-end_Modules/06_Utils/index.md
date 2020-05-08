# Utils ☔️

This document describes utilities written to this project

## List

- **createSchemaRef(targetModel)** - create mongoose reference object to given [ModelNames](../08_Connection/index.md).targetModel
- **LogOnError\[Sync\]** - try/catch wrapper as method decorator
- Route utilities described in different module. See [Routes](../07_Routes/index.md)

## Example

### createSchemaRef()

```ts
import { Schema } from "mongoose";
import { ModelNames } from "@/@types";
import { createSchemaRef } from "@/utils";

const schema = new Schema({
  // mongoose reference to future populate() features
  referenceToUser: createSchemaRef(ModelNames.USERS),
});
```

### LogOnError\[Sync\]

```ts
import { LogOnError, LogOnErrorSync } from "@/utils";

class SomeService {
  @LogOnErrorSync
  public someSyncMethod() {
    /* code possibly throwing exception */
  }

  @LogOnError
  public async someAsyncMethod() {
    /* code, promise possibly throwing exception */
  }
}
```
