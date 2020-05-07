# Event Pipe 🕦️

This document describes Event pipe and Events themselves.

Event Pipe in systems generally looks like this:
![event-pipe](./../img/event-pipe.png);

Services are listening or emitting events to a single EventEmmiter instance.

Events are defined in different namespaces separated with double colon sign `namespace::sub-namespace::event-name`

List of events could be found [here](./Events.md)

**Note:** EventEmitter2 will be replaced by redis due to the Nginx load balancing.

## Usage

If you want to fire an event not registered at docs, do not forget to document your event.

If you want to listen to one of the defined events, then follow:

```ts
import pipe from "@/pipe"; // pipe object
import { EventNames } from "@/@types";
import Logger from "@/services/logger";

pipe.on(EventNames.SERVER_CLOSE, () => {
  // logging fact of handling the event
  Logger.handled(Event.SERVER_CLOSE, "Some Module", "Some Message");

  /* handler code */
});

pipe.emit(EventNames.SERVER_CLOSE);
```

Notes on `EventNames` enum. It contains all the defined events in the system, so must be **always** used in listening or emitting events.

```ts
export enum EventNames {
  SERVER_CLOSE = "server::close",
  SERVER_SETUP = "server::setup",
  MONGO_CONNECTED = "mongo::connected",
}
```
