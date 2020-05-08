# Logger ✍️

```ts
class Logger {
  static route(req: express.Request): void;
  static fired(name: EventNames): void;
  static handled(name: EventNames, who: string, message: string): void;
  static error(who: string, message: string): void;
  static log(message: string): void;
}
```

Logger object writes to a console in development mode.

- **route** - used in `logger()` middleware, logging api calls
- **fired** - logs fired [Event](../04_Pipe/index.md)
- **handled** - logs fact of handling the [Event](../04_Pipe/index.md)
- **error** - logs error happened in system
- **log** - simple log

## route()

```ts
app.get("/api", (req: express.Route, ...) => {
  /* route code */

  // api call will be logged
  Logger.route(req);

  /* route code */
});
```

## fired()

```ts
// listening to all events
pipe.on("**", function () {
  // this.event holds the name of the event
  Logger.fired(this.event);
});
```

## handled()

```ts
// ServerService.js
import { EventNames } from "@/@types";

pipe.on(EventNames.SERVER_CLOSE, () => {
  /* 
    logging the fact, that someone handled the event
    name - name of the event
    who - who is handling it
    message - custom message describing shortly what handler will perform
  */
  Logger.handled(EventNames.SERVER_CLOSE, "Server Service", "closing server");
});
```

## error()

```ts
try {
  /* complex code */
} catch (err) {
  Logger.error("Someone", err);
}
```

## log()

```ts
Logger.log("something....");
```
