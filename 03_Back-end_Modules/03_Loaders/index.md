# Loaders 🛫

This document describes loading process

Table of contents:

- [Loaders 🛫](#loaders-%f0%9f%9b%ab)

Loading main function asynchronously executes different parts of the system in order to start it.

Order of execution:

1. Configs are initializing. See [Configs](../02_Configs/index.md)
2. Event Pipe object is being created. See [Pipe](../04_Pipe/index.md)
3. [server::setup](../04_Pipe/Events.md#serversetup-event) event is fired
4. Database connection is being established. See [Database](../../05_Database/index.md) and also notes on [Connection](../08_Connection/index.md)
5. Express application is created with middleware plugins. See [Plugins](../01_Packages/index.md)
6. Services are being invoked. See [Services](../05_Services/index.md)
7. Route collector, collects all the controllers from `route` directory and places them to express app. See [Routes](../07_Routes/index.md)
