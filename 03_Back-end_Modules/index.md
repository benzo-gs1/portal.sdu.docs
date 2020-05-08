# Back-end reference

This document describes Back-end dependencies, services, loaders, configurations and etc...

- [Packages](./01_Packages/index.md)
- [Configs](./02_Configs/index.md)
- [Loaders](./03_Loaders/index.md)
- [Event Pipe](./04_Pipe/index.md)
- [Routes](../01_Rest_Api/index.md) - This part is described in REST Api reference
- [Services](./05_Services/index.md)
- [Utils](./06_Utils/index.md)
- [Routes](./07_Routes/index.md)
- [Connection](./08_Connection/index.md)

## yarn scripts

We use `yarn` instead of `npm` for it's simplicity and speed

- `start:dev` - runs nodemon
- `start:prod` - runs builded app
- `start` - alias of `start:prod`
- `test:dev` - runs mocha tests in development mode
- `test:prod` - runs mocha tests in production mode
- `test` - alias of `test:dev`
- `build:check` - runs typescript for validating code types and many other things
- `build:run` - runs babel typescript preset for compiling code into `build` folder
- `build` - runs both type checking and compiling
