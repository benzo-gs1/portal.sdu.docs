# Events 📅

Table of contents:

- [Events 📅](#events-%f0%9f%93%85)
  - [server](#server)
    - [server::close event](#serverclose-event)
    - [server::setup event](#serversetup-event)
  - [mongo](#mongo)
    - [mongo::connected event](#mongoconnected-event)

## server

All events related to server activity

### server::close event

Server is ready to close

**Fired by:** [test server route](../../01_Rest_Api/03_Server/01_kill.md)
**Handled by:** [ServerService](../05_Services/02_ServerService.md)

### server::setup event

Server setup is finished

**Fired by:** [Main Loader function](../03_Loaders/index.md)

## mongo

All event's related to database activity

### mongo::connected event

Database connection is established

**Fired by:** [Database loader function](../03_Loaders/index.md#database)
