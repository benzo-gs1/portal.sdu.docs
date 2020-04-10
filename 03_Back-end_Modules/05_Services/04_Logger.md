# Logger ✍️

```js
class Logger {
  static route(req);
  static fired(name);
  static handled(name, who, message);
  static error(who, message);
  static log(message);
}
```

Logger object writes to a console in development mode.

- **route** - Logs Express.Route request object
- **fired** - Logs a fired EventEmmiter2.Event object
- **handled** - Logs a fact of handling the event
- **error** - Logs error or exception
- **log** - Simple log message

## route()

```js
app.get("/api", (req, res) => {
  /* route code */

  // route information will be logged
  Logger.route(req);

  /* route code */
});
```

## fired()

```js
pipe.on("**", function () {
  // this.event holds the name of the event
  Logger.fired(this.event);
});
```

## handled()

```js
// ServerService.js

pipe.on("server::close", () => {
  /* 
    logging the fact, that someone handled the event
    name - name of the event
    who - who is handling it
    message - custom message describing shortly what it will do
  */
  Logger.handled("server::close", "Server Service", "closing server");
});
```

## error()

```js
try {
  /* complex code */
} catch (err) {
  Logger.error("Some Service", err);
  process.exit(1);
}
```

## log()

```js
Logger.log("something....");
```
